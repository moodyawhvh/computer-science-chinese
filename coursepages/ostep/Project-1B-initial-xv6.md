> 🌐 本文档由 [ossu/computer-science](https://github.com/ossu/computer-science) 翻译,英文原版见原项目。

## 项目 1B

### 全部感谢 [palladian](https://github.com/palladian1)

### Linux 环境安装

* 确保你有兼容的编译工具链;在 Linux 上 gcc 完全够用。
* 安装 qemu-system-x86(在不同发行版上可能叫 qemu-system-i386 或 qemu-system-x86_64;注意某些发行版里名为 qemu 的包是错的)。
* 安装 Perl。
* 安装 gawk。
* 安装 expect。
* 在与项目测试脚本相同的目录下建一个 src/ 目录。
* 克隆 xv6 的 GitHub 仓库,把源码复制到你的 src/ 目录中。
* 在 src/ 内运行 `make qemu-nox` 测试 xv6 能否正常工作。用 `Ctrl-a x` 退出 xv6;如果忘了,也可以直接杀掉 qemu 进程。建议用 `top` 或 `htop` 确认 qemu 已经不在运行;有时它在你退出后仍会继续运行并占用大量资源。
* 修改 Makefile,设置 `CPUS := 1`。
* 再次运行 `make qemu-nox`,确认 xv6 仍能正常工作。

### 任务说明

* 你的任务是为 xv6 新增一个系统调用 `getreadcount()`,返回此前发生的 `read` 系统调用的次数。注意这个计数必须是全局计数,而不是按进程的计数。

### 建议做法

* 下载 xv6 源码 PDF(它的排版比下载下来的代码更易读)。先看目录,弄清"页(sheet)、页码(page)、行号"的编号方式,再浏览后面的交叉引用,以便需要时能快速定位代码。
* 非常快速地浏览一下目录中 `processes` 和 `system calls` 部分列出的源码文件,以及 user-level 部分的 `usys.S`。先不求看懂,只需要知道每个文件在 PDF 里的位置,方便稍后跟着讨论视频走,因为教授的代码目录结构和你的不一样。
* 观看项目 P1B 的讨论课 2(discussion 2)视频,对照你手里的 xv6 代码 PDF,在教授讲解每个部分的作用时做好批注。
* 阅读项目 GitHub 页面上链接的背景资料,同时在 xv6 代码 PDF 上做批注。
* 再通读一遍 xv6 PDF,这次目标是整体理解 `processes` 和 `system calls` 两节,以及 `usys.S` 和 `user.h`(注意:最后一项不在 xv6 PDF 里,你需要看实际下载的代码)。不必逐行看懂,只要弄清系统调用在哪里定义、如何被调用等即可。
* 修改 xv6 源码,添加新的 `getreadcount()` 系统调用。你需要改动多个文件;建议给自己的改动加上 `// OSTEP project` 标记,方便之后调试时查找。
* 还有一处需要加代码的地方不在 xv6 PDF 里:`user.h`。
* 完成后运行测试脚本。测试 1 会运行一个发起多次 `read` 调用的函数,然后调用 `getreadcount`。要让代码通过,你必须正确统计所有进程发出的 `read` 调用总数。
* 如果通过了测试 1,恭喜!现阶段任务完成。在学习并发相关课程之前,不用管测试 2。
* 如果没通过测试 1,可以把 `tests/1.out` 中的期望输出与你自己的实际输出 `tests-out/1.out` 对比,也可以查看 `tests-out/1.err` 里的错误信息。
* 你也可以在终端里用 `make qemu-nox` 启动 xv6 来手动测试。输入 `ls` 查看所有文件,应该能看到 `test_1` 和 `test_2`。用 `./test_1` 运行测试 1 并观察输出,可以手动与期望输出对比。
* 学完线程、并发与锁的课程之后:测试 2 检验你的 `getreadcount` 实现是否线程安全。之前八成不是线程安全的,解决办法是加一把锁。然后重新运行测试脚本,确认两个测试都能通过。
