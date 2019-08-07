---
title: 解决 Python “Microsoft Visual C++ 14.0 is required.” 问题
date: 2019/8/6 20:20:00
---

别在 Windows 上用 Python ，大概是个劝告吧，就算你解决了这个问题，还会有别的问题等着你。
不过标题都写了，还是要讲一下怎么解决的。

 - 1.打开微软 VS 官方的下载页面 https://visualstudio.microsoft.com/zh-hans/downloads/ 。
 - 2.往下找到 “Visual Studio 2019 工具” 选项卡，下载 “Visual Studio 2019 生成工具”。
 - 3.运行下载好的安装包，勾选 “工作负载” 选项卡中的 “C++ 生成工具” 后，勾选右侧安装详细信息中的 “MSVC v141”、“MSVC v140” 并开始安装。

问题解决。
