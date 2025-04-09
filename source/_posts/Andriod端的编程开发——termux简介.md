---

title: Termux简介
date: 2024-05-03 22:30:55
tags: 
- Termux
- Andriod
categories: 
- 技术

---

# Termux in Andriod

Andriod 端的命令行终端：[Termux](https://termux.dev/en/)

入手了xiaomi pad 6之后，我想要在 Andriod 端做一些简单的编程开发，第一个想到的就是下载 `VScode`，但是它没有 Andriod 发行版......（不可能，我一定要在平板上跑vscode），于是我开始折腾终端环境。在被 Node.js 的发行版反复折磨之后，我终于发现原来 Termux 的包管理工具 `pkg` 中就自带了 `VScode`(code server)。嗯，看起来不错，终于能在 localhost:4000 看到熟悉的 Visual Studio code 页面了，但是这个启动速度实在太慢了，JavaScript 果然是依托。在编辑我的 bash 配置时，我使用了 vim ，从此发现新天地......由于我的电脑是游戏本，携带过于笨重，所以有时一台平板也可以成为我的开发平台，更加便携

安装 Termux 之后，可以开启设备的存储权限:``termux-setup-storage``[^1], 之后使用 `cd`命令导航进入 `storage`目录即可

接下来可以使用 Termux 的包管理工具 `pkg`，首先使用 `pkg upgrade`更新安装库，之后可以使用 `pkg install`命令安装库:

```textile
pkg install python c java git 
```

注意 `pkg install`命令可以接受多个参数

简单的环境配置之后就可以进行编程开发。由于 Termux 是类 Linux 环境，支持原生 vim 编辑器，因此使用 vim 可以带来极为舒爽的编程体验，关于 vim 这里只介绍几个简单的编辑模式：

按键 [i] 进入 `insert`插入模式，命令行指令 `:wq`保存编辑并退出，另外可以通过[h][j][k][l]控制方向，完全解放右手不碰鼠标

[^1]: [Termux-setup-storage - Termux Wiki](https://wiki.termux.com/wiki/Termux-setup-storage)
