---
title: 验证 Telegram MTProto Proxy 代理服务器
date: 2018/6/24 00:32
---

由于在日常会使用到 Telegram 聊天，WiFi环境下有路由处理流量，而用4G的时候手机不挂VPN就没办法使用了，这时发现在 Telegram 内置的代理设置里包括 Socks5、HTTP、MTProto 三种代理协议。

其中 Socks5 和 HTTP 都是大家熟悉的代理协议，稳定性和性能也都比较差，而新发现的这个 MTProto 应该是 Telegram 自研的代理协议，在 Telegram 使用这个自研的代理协议应该是最可靠的方案，于是我开始查找关于 MTProto 代理服务器的资料，并搭建了一个 MTProto 协议的代理服务器。

首先，我找到了 MTProto 代理服务器的官方机器人 @MTProxybot ，开始会话后，会发送一个说明，提示在 [Docker Hub](https://hub.docker.com/r/telegrammessenger/proxy/) 可以下载到 Telegram 代理服务器的软件，通过 Docker 快速部署一个代理服务器。

* 安装 Docker

```
curl -sSL https://get.docker.com/ | sh
```
* 运行 MTProto 代理服务器

```
docker run -d -p443:443 --name=mtproto-proxy --restart=always -v proxy-config:/data telegrammessenger/proxy:latest
```

成功运行 MTProto 代理服务器后，通过``docker logs mtproto-proxy``可以查看代理服务器密钥。

回到 @MTProxybot 机器人，发送``/newproxy``指令创建一个用于代理服务器的标签，这样就可以在机器人进行状态查询和绑定频道的操作。

* 创建成功示例

```
Success!
Your proxy has been successfully registered.
You can now pass this proxy tag to the software you are using: 0b42fca6d61e98001855b1af95461dbe.
```
>其中``0b42fca6d61e98001855b1af95461dbe``就是用于代理服务器的标签。

获得标签后，停止并删除原来创建的 Docker 容器，重新运行一个带有 TAG 参数的容器。
```
docker stop mtproto-proxy
docker rm mtproto-proxy
docker run -d -p443:443 --name=mtproto-proxy --restart=always -e TAG=0b42fca6d61e98001855b1af95461dbe -v proxy-config:/data telegrammessenger/proxy:latest
```
>由于 Docker 卷 proxy-config 并没有被删除，所以代理服务器密钥并不会发生变化，此时所有的搭建工作就已经完成。

点击机器人提供的快速连接链接，即可连接到自己搭建的 Telegram MTProto Proxy 代理服务器。
