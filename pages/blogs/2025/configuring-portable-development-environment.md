---
layout: blogs
title: 配置便携开发环境（MSYS2、Windows Terminal）
permalink: tech/configuring-portable-development-environment
date:
license: CC BY-SA 4.0
---

# 配置便携开发环境（MSYS2、Windows Terminal）

# 零、前言

其实写这篇 Blog 的意义不大，因为很少有人会像我一样，需要在一个会自动还原的学校机房电脑上，用移动硬盘配置一个便携式的开发环境。但是我花了挺长时间来配这个，所以还是写一写吧，顺便也用来测试一下搭的 Blog。

配置这个环境用的是 MSYS2 + Windows Terminal（后文简称 wt），因为我主要是想要一个轻量化、免安装的 Shell 环境，并且能在里面用一些基本应用（Git 之类的），不指望搞大型开发。MSYS2 基本能满足我的需求。至于 MSYS2 自带的 mintty 我实在是不喜欢，wt 看起来更美观一点。

关于 MSYS2 和 wt，请善用搜索引擎。

# 一、准备工作

需要准备的材料：

1. 能够正常连接 GitHub 并下载文件的电脑

2. 一个便携存储设备（U 盘、移动硬盘等，不然配这个干什么）

# 二、配置 MSYS2

> MSYS2 是一个在 Windows

首先，在 [MSYS2-Installer Releases](https://github.com/msys2/msys2-installer/releases) 页面，下载最新的、带有 `x86_64` 和 `sfx.exe` **且没有后缀**的文件（如 `msys2-base-x86_64-20251213.sfx.exe`）。运行，把文件解压到将要安装的目录（解压之后再移也可以），建议套一层文件夹。

* 如果你的电脑是 ARM64 架构，那么请把上述过程中的 `x86_64` 换成 `arm64`。不过我没见到过 ARM64 架构的电脑。

运行 `msys64.exe`（其实别的也可以），等待初次配置完成，然后关掉。

用编辑器打开 `安装目录/etc/nsswitch.conf`，把 `db_home:` 后面的内容改成 `/home/用户名`。

到这里，MSYS2 的配置就已经完成了。

*猜测：改 `nsswitch.conf` 应该是把所有用户的 `home` 重定向了，因此即使换了一台机器，用户改变了，仍然用的是一套文件。这样做会导致多用户不能用，但是本来就没打算用。*

# 三、配置 wt

和配置 MSYS2 类似，先在 [wt Releases](https://github.com/microsoft/terminal/releases) 下载符合你系统架构的 ZIP 包（是下 Release 还是 Pre-Release 看个人喜好，毕竟不会自动更新），解压到与 MSYS2 并列的路径。

这个时候文件路径大概长这样：

	root
	|-MSYS2
	| |-msys64.exe
	| |-...
	|-WindowsTerminal
	  |-wt.exe
	  |-...

*不按这个目录配置也可以，但是你得确保后续牵扯到路径的步骤都能换成对应的路径。*

修改记录：

2025/12/21 周日 着手撰写