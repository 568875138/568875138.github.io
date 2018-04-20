---
title: Shadowsocks Docker 版
date: 2018/4/16 20:20:00
---

-----BEGIN PGP SIGNED MESSAGE-----
Hash: SHA256

Shadowsocks 是一种基于 Socks5 代理方式的网络数据加密传输工具。Shadowsocks 分为服务器端和客户端，在使用之前，需要先将服务器端部署到服务器上面，然后通过客户端连接并创建本地代理。

使用 Dockerfile 可以轻松的构建自己的镜像，再通过 Docker Hub 提供的自动构建机，我制作了一个 Docker 版的 Shadowsocks，可以在 Docker 机器上轻松的创建管理 Shadowsocks 服务而不用考虑 Shadowsocks 的依赖问题，同时隔离的运行环境也提高了一点安全性。

https://hub.docker.com/r/silentyang/shadowsocks/
-----BEGIN PGP SIGNATURE-----

iQIzBAEBCAAdFiEE50PHlF7RqNYeJun8O0fJBBWnAWYFAlrI5LoACgkQO0fJBBWn
AWazNA//VRM0ShrQ/q34HDk70GE+8rvIDgUwntdZaD4y1ayGwU5lkYumcNt9yIyP
+0x3c0Z2xe4psyOwhkrRu9DkuomxSiZiojbBNYJyyMeZbusiagm2UFx72+/CGNF3
kMGbrar9LGARs/UmoJRTVbbAV5KY/bXxl617Rif6gZpiS58bFZT2jML6IY6YIcrt
fnRzCedQFXP/bemjxjijIfHLVPyPcwERW9DBkcx2E2ygj5Qm4AVu64wWmkAlII3R
lcaxf8HsSnrmRw5LaTEYIbGd+0hgMzka4sm2jeIu0JLWtb43De2tNtNw/A0fr6OK
mMmFt3BJF7WXYOhY2D3dYqSlOjqnuCbXTDQ0AMucP1N72ls7COfaXmwZ99NuyCTf
zGkAiAEzWjToPAOpUMIkISekNtkHCn4p+yuyZz6IjOtv8QkvLn9oA7LnMy7baenw
DKHoPtHBek8fhLtRtsA6/By68sXRtvT4akFRzsL/mt1AR6TswF65NWi6fxtEhFp/
FcEowYabFDdXX+DQh8GfI1So651fr4XS0XZsTvxoMbh36j6qfaHH2Sr3o2up/o7e
Rlem6eORYVWIn4lwznnxs8fNQqtB4Jt/10xOxLk/wiV4Zqwyaq1rlkAGjcPjfVJh
/J4RiKlSiT26r1nWe9p+P6VrLTZlOFhfxSVOVoh6TX5op0LkFWk=
=svgU
-----END PGP SIGNATURE-----
