# Linux Configuration files Collection

## 项目简介

这是一些关于 Linux 内核的配置文件。为了方便以后的内核编译，所以收集了一些。

其中有我自己配置的，也有一些是提取自一些比较知名的 Linux 发行版的。



**从 2022 年 9 月 24 日开始，本项目将在内核版本的 deblob 文件夹中附带 Linux 内核专有代码清除脚本，来自 [FSFLA: GNU Linux-libre project](http://www.fsfla.org/ikiwiki/selibre/linux-libre/)，依照其原有许可证（GPLv2）进行发布。**

**请注意，清除专有代码后，编译出来的 Linux 内核在一般情况下将无法驱动目前市面上相当一部分的硬件，仅供 Free Software 爱好者和 Linux 内核研究者使用。**



国内分流：[kernel-config: Linux kernel configuration files collection. (gitee.com)](https://gitee.com/njlyf2011/kernel-config)



## 文件说明

配置文件已经按照内核版本和来源而分类。

其中，带有 `-gnu` 字样的配置文件，是适用于 [Linux Libre](https://en.wikipedia.org/wiki/Linux-libre) 的。

带有 `-def` 字样说明是经过 `make defconfig` 命令生成的默认配置内核（默认配置内核不代表完善，反而很多东西需要自己配置）。

带有 `-mini` 字样说明是经过了 `make allnoconfig` 命令生成的最小化内核，排除了所有可选项，并且不是 x86-64 内核（需要自行开启）。

`-allyes` 表示是经过 `make allyesconfig` 命令生成的带所有可选项的内核配置，但是请注意，`make allyesconfig   `生成并编译出来的内核通常是**无法正确使用**的。 因此仅供参考。

带有 `-luke` 的则表明这个是我自己配置的。

来自一些 Linux 发行版的配置文件也已经在文件名里面标出，比如 `config-5.15.0-43-generic-ubuntu`。



要使用这些配置文件，您可以将其中一个配置文件复制到 Linux 的源码根目录下，然后输入 `make oldconfig` 进行适配，一些发行版的配置文件可能和主线内核不兼容，因此需要进行其他修改。



## 配置的可靠性

收集的来自一些知名的 Linux 发行版的内核配置文件经过测试目前是可靠的。如果发行商有后续的更新我也会继续跟进。

一些发行版的内核配置文件是针对他们自己 patch 过的内核而进行编写的，所以在主线的 Linux 内核上可能需要进行一定的修改方可编译通过。比如 Ubuntu 的内核配置文件里面涉及到了主线内核所没有的关于安全启动的配置。

关于我自己的内核配置文件，我能保证在我的测试里是过关的，但由于每个人使用的环境不同，所以每个人的使用需求和期望是不一样的，我的配置文件仅供参考，不建议用于日常或者生产环境，也不能保证您满意。

至于目前处于开发版本的内核的配置文件，您应当清楚尚未正式发布的版本是存在大量 bug 的，所以仅供测试用途。

此外您在使用这些配置文件时最好对应内核版本，不然不能保证您能使用当前内核增加的新功能。



## 项目授权

来自 Linux 发行版的配置文件遵照原来授权。

我自己配置的文件在 MIT 许可下发行。







