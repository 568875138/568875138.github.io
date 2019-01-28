---
title: Nintendo Switch 破解系统《大气层》编译环境
date: 2019/1/28 18:33
---

```
FROM devkitpro/devkita64
MAINTAINER elelphatp "elephantp@elephantp.blog"

RUN dkp-pacman -Syyu --noconfirm devkitARM && \
    dkp-pacman -Scc --noconfirm && \
    git clone --recurse-submodules  https://github.com/switchbrew/libnx && cd libnx && \
    make && make install 

ENV DEVKITARM=${DEVKITPRO}/devkitARM

WORKDIR /developer

ENTRYPOINT ["make"]
```
