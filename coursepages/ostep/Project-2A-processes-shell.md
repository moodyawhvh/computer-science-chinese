> 🌐 本文档由 [ossu/computer-science](https://github.com/ossu/computer-science) 翻译,英文原版见原项目。

## 项目 2A
### 全部感谢 [Palladian](https://github.com/palladian1/)

- [x] 交互模式
- [x] 批处理模式
- [x] exit
- [x] cd
- [x] path
- [x] 输出重定向
- [x] 并行命令

### 提示

* 先观看 Unix shell 讨论课 3( discussion 3)的视频。
* 阅读 OSTEP 书籍第 5 章。
* 从只做一件事的 shell 开始:打印提示符,输入 `exit` 时退出。然后加 `cd`,再加 `path`。接着实现用 `execv` 执行命令,然后加批处理模式,再加重定向,最后实现并行命令。
* 所有测试脚本都会用到批处理模式和重定向,所以在完成这两项之前,你只能手动测试 shell。
* 实现 `path` 命令时,确保既能处理绝对路径也能处理相对路径(即 `path tests` 和 `path /usr/bin` 都要能用)。
* 错误信息的细节很容易踩坑,所以先在看起来合理的地方都加上错误信息,然后跑测试脚本,反复修改代码,直到错误报告的时机与要求完全一致。跑第 i 个测试时,可以查看 `tests/i.err` 和 `tests/i.rc`,看 shell 应该产生多少错误,再与 `tests-out/i.err` 和 `tests-out/i.rc` 对比。
* 如果测试 3 期望输出形如 `ls: cannot access ...`,而你的 shell 输出 `/bin/ls: cannot access ...` 或 `/usr/bin/ls: cannot access ...`,试着把 $PATH 环境变量改成以 `/bin` 开头。如果还不行,直接修改 `tests/3.err` 来匹配你系统的输出即可。不改 `ls` 和/或 `execv` 的实现就无法改变系统输出,所以只要语义上工作正常,跳过这个测试也没问题。
* 由于我系统的配置原因,我不得不修改 `/tests/3.pre` 改用 `/bin/ls` 才通过全部测试。或者你也可以在 `.profile` 或 `.bashrc` 里加上 `export PATH="/bin:$PATH"`。

### 内存管理的陷阱与坑

* 这个作业非常容易制造指向栈变量的指针,而变量一出作用域就不复存在,从而导致段错误(segmentation fault)。务必保证:如果你让一个指针指向字符串,那个字符串必须是你在堆上分配的,而不是栈上的。

* 话虽如此,如果你确实用了栈上的字符串,可以用 `strcpy()`、`strncpy()`、`strcat()`、`strncat()` 把它复制进堆分配的字符串。

* `strcpy()` 和 `strcat()` 只用于固定长度的字符串,并确保目标缓冲区足够容纳整个字符串外加一个 `\0` 结尾符。

* 对于 `strncpy()` 和 `strncat()`,确保 `n` 足够容纳 `\0` 结尾符,或者手动补上。

* 小心 use-after-free(释放后使用),尤其是在实现 `path` 时。

* 记得释放来自 `getline()` 和 `strdup()` 的字符串,但也要小心双重释放(double-free),例如不要释放某个已释放字符串的子串。

* 避免使用 C 库函数 `strtok()`;它不是线程安全的。改用 `strsep()`。

* 使用 `strsep()` 时,务必保留一份指向原始字符串的指针副本,以便之后释放,因为 `strsep()` 会修改指针本身;如果之后释放的是被改过的指针,你会破坏页表。

* 调用 `strsep(&buf, delim)` 之后,解引用 `buf` 前先检查它是否为 `NULL`。
* C 语言通用实践:在某个函数里为数据结构分配的内存,应在同一个函数里释放。如果你在专门的 `create_xxx` 函数里分配内存,就应有对应的 `destroy_xxx` 函数。这样内存的分配与释放总是发生在同一函数层级,更容易避免内存错误。
* 每次调用 `malloc`、`calloc` 或 `realloc` 之后,检查返回值是否为 `NULL`。
* 创建指针数组时用 `calloc` 而不是 `malloc`,避免产生指向垃圾值的指针。
* 在 `update_path` 里我修过这个问题:大多数测试用 `path /bin /usr/bin`,但有一个用 `path tests`。所以我假定:路径以斜杠开头就是绝对路径,原样复制;否则就是相对路径,要在开头加上 ./。
