---
layout: blogs
title: 配置便携开发环境（MSYS2、Windows Terminal）
permalink: tech/configuring-portable-development-environment
date: 2025/12/21
---

# 配置便携开发环境（MSYS2、Windows Terminal）

# 一、前言

其实写这篇 Blog 的意义不大，因为很少有人会像我一样，需要在一个会自动还原的学校机房电脑上，用移动硬盘配置一个便携式的开发环境。但是我花了挺长时间来配这个，所以还是写一写吧，顺便也用来测试一下搭的 Blog。

配置这个环境用的是 MSYS2 + Windows Terminal（后文简称 wt），因为我主要是想要一个轻量化、免安装的 Shell 环境，并且能在里面用一些基本应用（Git 之类的），不指望搞大型开发。MSYS2 基本能满足我的需求。至于 MSYS2 自带的 mintty 我实在是不喜欢，wt 看起来更美观一点。

# 二、准备工作

需要准备的材料：

1. 能够正常连接 GitHub 并下载文件的计算机

2. 一个便携存储设备（U 盘，移动硬盘等，不然配这个干什么）

# 三、配置 MSYS2




修改记录：

2025/12/21 周日 着手撰写，写完第一节和第二节