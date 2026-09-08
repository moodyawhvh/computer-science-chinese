> 🌐 本文档由 [ossu/computer-science](https://github.com/ossu/computer-science) 翻译,英文原版见原项目。

## 全部感谢 [palladian](https://github.com/palladian1)

### 通用提示

* 阅读 OSTEP 书籍第 9 章,并观看讨论课 5 的视频。彩票调度器(lottery scheduler)在授课视频里没讲,所以这部分真的必须读书。

* 一般来说,内核里不能用 C 标准库函数,因为内核必须先完成自身初始化,才能执行库的二进制代码。

* xv6 内核有一个"内核版" `printf`;它多接受一个整数参数,用来指定输出到 `stdout` 还是 `stderr`。注意它只支持 `"%d"` 这类基本格式串,不支持 `"%6.3g"` 这种复杂格式;解决办法是手动补空格。内核里还有一个类似的函数 `cprintf`。

* 如果你确实想用内核里没有的其他库函数(如伪随机数生成器),可以参考 P.J. Plauger 的《The Standard C Library》里这些函数的实现,然后自己动手写。

  ### 实现要点

  * 添加两个新系统调用时,要修改的文件和项目 1b 相同。
  * 理解进程如何创建:记住进程先处于 `EMBRYO` 状态,之后才变为 `RUNNABLE`——你要找到这个转换发生的位置。
  * 系统调用的参数类型固定为 `void`,所以看看 `kill`、`read` 这类系统调用是如何绕过这个限制、从用户空间拿到参数(整数和指针)的。你可能需要沿着调用链往前倒几步。
  * 凡是需要访问内核其他部分代码的地方,确保包含 `types.h` 和 `defs.h`。
  * 要实现 xv6 命令 `ps`,先看看 `cat`、`ls`、`ln` 是怎么实现的。别忘了修改 Makefile,把 `ps` 的源码加进编译。

## 剧透警告!

### 解法走查(节选)

- 从一份全新的 `xv6` 源码副本开始。

- `argint` 和 `argptr` 是关键函数。系统调用本身不带参数,但用户代码里实际上要给它传参数。

- 做法是:内核先调用无参的 `sys_kill()`,再由 `sys_kill` 用 `argint()` 从调用栈里取出参数,传给真正的 `kill(int pid)`。

- `syscalls.c` 里那一堆 `extern int sys_whatever` 声明,表示这些函数定义在别的文件里,会以函数指针形式引入。真正的系统调用实现不带 `sys_` 前缀,这些 `sys_whatever` 只是包装函数。所以要把 `sys_settickets` 和 `sys_getpinfo` 加进声明列表。

- 接着是一个函数指针数组,用的是老式 C 初始化写法 `int arr[] = { [0] 5, [1] 7}`。方括号里的 `SYS_fork` 等名字是 `syscall.h` 里定义的宏。要在数组里加两个指向 `sys_settickets`、`sys_getpinfo` 的条目,并在相应头文件里定义 `SYS_settickets` 和 `SYS_getpinfo`。

- 这些 `sys_` 包装函数定义在 `sysproc.c`。在那里创建 `int sys_settickets(void)` 和 `int sys_getpinfo(void)`。

- 真正的 `settickets` 需要 int 参数,用 `argint` 从调用栈取出来传给它;`getpinfo` 需要指针,用 `argptr`。`sys_settickets` 的 if 语句里多了一个条件,因为票数不允许小于 1。

- 每个系统调用还有一段汇编要执行;好在它只是预写好的宏,在 `usys.S` 末尾加两行 `SYSCALL(settickets)` 和 `SYSCALL(getpinfo)` 即可。

- 系统调用的最后一部分:在 `user.h` 里声明它们,用户代码才能调用。`struct pstat` 完整定义在 `pstat.h`,但 `user.h` 里也要声明,免得用户代码报错。所有使用系统调用或 xv6 标准库的用户代码都要包含 `user.h`。

- 至此,操作系统层面两个系统调用的接线全部完成;接下来才是用普通函数 `settickets` 和 `getpinfo` 实现功能,然后实现调度器和 `ps` 程序。

- `pstat.h` 不是给调度器用的,是给 `ps` 程序用的(类似 Linux 的 `ps`),它只定义 `struct pstat`,没有对应的 .c 文件。

- 调度器的工作方式:进程创建时默认分配 1 张票;之后进程可以通过 `settickets` 系统调用自己设票数。

- 第一步在 `proc.h`:进程由 `struct proc` 表示,给它加一个成员 `int tickets`。`int ticks` 成员是给 `ps` 用的,后面再说。

- `proc.h` 里的 `enum procstate` 列出了所有可能的进程状态。`EMBRYO` 表示正在创建;我 `grep` 了 `EMBRYO`,找到进程创建的位置来设置默认 1 张票——在 `proc.c` 里。

- `proc.c` 中的 `allocproc` 负责初始化进程:遍历进程表 `ptable` 找未使用的槽位,找到后创建进程;我在那里加了 `p->tickets = 1;`。

- 下一个改动对应一条需求:子进程要继承父进程的票数。子进程由同一文件里的 `fork` 创建,其中 `curproc` 是当前进程,`np` 是新进程,于是设 `np->tickets = curproc->tickets`。

- 调度器需要生成一个伪随机数,然后把计数器从 0 开始遍历进程表,把每个进程的票数累加到计数器上;计数器一旦超过伪随机数就停下,运行那个进程。

- 伪随机数我是照着 P.J. Plauger 的《The Standard C Library》(一本带注释的 C 库源码大全)实现的 `rand` 和 `srand`:`srand` 设随机种子,`rand` 把它变成伪随机整数。其中整数与无符号整数之间来回转换的类型技巧,是为了避免有符号整数溢出(未定义行为);无符号溢出则没问题。我只做了一处提速:把 `% 32768` 写成 `& 32767`。

- 我用的"随机"种子是 `ticks`(计时器中断次数)——第一次运行是 0,然后 1、2……完全谈不上随机。关于 `ticks` 计数的几行代码是给 `ps` 用的,与调度器无关。

- 把它变成彩票调度器的核心改动就是计数器变量,外加一个统计已发彩票总数的 for 循环。

- 上下文切换(原版代码,5 行):

  ```c
  c->proc = p;
  switchuvm(p);
  p->state = RUNNING;

  swtch(&(c->scheduler), p->context);
  switchkvm();
  ```

  流程:先拿锁(最后才释放);for 循环遍历 `ptable`,只挑 `RUNNABLE` 的进程(这是原有的轮转调度);找到第一个 `RUNNABLE` 进程后,`c`(当前 CPU)设为运行它;`switchuvm(p)` 建立该进程的虚拟内存地址空间,状态置为 `RUNNING`;`swtch` 是魔法所在——把 OS/调度器的寄存器内容换出,换入保存在内存里的进程 `p` 的寄存器内容。`swtch` 一执行,CPU 继续执行的就是进程的指令了,调度器函数停在那里。之后计时器中断到来时,处理器会用参数相反的 `swtch` 调用换回调度器的寄存器、保存进程的寄存器,并从断点继续执行。`switchkvm` 则切回内核的虚拟内存地址空间。

- 原版源码结构(伪代码):

  ```python
  while (1) {
    iterate over processes:
      if not runnable:
        continue
      run it
  ```

- 新代码结构(伪代码):

  ```python
  while (1) {
    count the total tickets allotted to all processes // 一个 for 循环
    get the winning ticket number
    iterate over processes: // 另一个 for 循环
      if not runnable:
        continue
      add its tickets to counter
      if counter <= winning ticket number:
        continue
      run it
  ```

- 非 `RUNNABLE` 进程的票直接忽略。票并不编号:每个进程只是持有一定数量的票,我们从头累加,直到越过第 `n` 张,`n` 即中奖号码。例如进程 A 有 5 张票、B 有 7 张、C 有 2 张:中奖号是 3 则 A 运行,8 则 B 运行,12 则 C 运行。0-4 归 A,5-11 归 B,12-13 归 C。

- `settickets` 很直白:拿锁、设票数、放锁。

- `getpinfo` 大致如下:`p` 是指向 `struct pstat`(定义在 `pstat.h`)的指针,其每个成员都是一个数组,每个进程占一项。先判空指针;遍历进程表,把第 i 个进程的对应值填进 `p` 的各成员第 i 项。

- 最后的收尾:在 `defs.h` 里加上 `struct pstat` 和 `settickets`、`getpinfo` 的声明;最后一个文件是 `ps.c`,实现类似 Linux `ps` 的程序——调用 `getpinfo` 填充 `struct pstat`,打印每个在用进程的信息;再改 Makefile 把 `ps.c` 加进编译,完工!

- 顺便解释为什么调度器里要记 `ticks`:`ps` 要打印每个进程运行了多久,所以需要统计它实际执行的时间片数。

- 最后在 `/src` 目录运行 `make qemu`,确认一切正常。

---

> 📝 **译注**:本文原文件超过 10000 字符,以上为核心章节完整翻译;"解法走查"一节为节选精编,保留了实现顺序、上下文切换代码与彩票算法示例等关键内容,省略了部分逐步口述细节,完整英文版见[原文](https://github.com/ossu/computer-science/blob/master/coursepages/ostep/Scheduling-xv6-lottery.md)。
