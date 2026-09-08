> 🌐 本文档由 [ossu/computer-science](https://github.com/ossu/computer-science) 翻译,英文原版见原项目。

致谢:[palladian](https://github.com/palladian1)

## xv6 虚拟内存入门

### 警告:

***本项目与当前能拿到的 xv6 源码不匹配——现版源码里已经实现了这个项目的内容!***

[palladian](https://github.com/palladian1) 从一位威斯康星大学学生的 GitHub 页面找来了另一个版本的 xv6 源码。我们不得不修改 `Makefile` 才能正确找到 QEMU 可执行文件,并在 `user` 文件夹中添加了 `null.c`(同时修改了该目录下的 `makefile.mk`),用来演示内存安全性的缺失。

从 [`start.zip`](https://github.com/spamegg1/reviews/raw/master/courses/OSTEP/ostep-projects/vm-xv6-intro/start.zip) 中的代码开始。解压后运行 `make clean` 和 `make qemu-nox`,然后在 xv6 系统内运行 `null`,亲眼看看内存安全缺失的后果!如果想把 `null` 的运行结果与实际机器码对照,可以运行 `objdump -d user/null.o`。

每次修改代码后,你可能都需要手动执行 `make clean` 和 `make qemu-nox`。
