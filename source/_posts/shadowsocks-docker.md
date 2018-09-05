---
title: Shadowsocks Docker 版
date: 2018/4/16 20:20:00
---

Shadowsocks 是一种基于 Socks5 代理方式的网络数据加密传输工具。Shadowsocks 分为服务器端和客户端，在使用之前，需要先将服务器端部署到服务器上面，然后通过客户端连接并创建本地代理。

使用 Dockerfile 可以轻松的构建自己的镜像，再通过 Docker Hub 提供的自动构建机，我制作了一个 Docker 版的 Shadowsocks，可以在 Docker 机器上轻松的创建管理 Shadowsocks 服务而不用考虑 Shadowsocks 的依赖问题，同时隔离的运行环境也提高了一点安全性。

https://hub.docker.com/r/silentyang/shadowsocks/
