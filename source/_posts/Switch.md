---
title: Nintendo Switch 破解系统《大气层》编译环境
date: 2019/1/28 18:33
---

```
FROM devkitpro/devkita64
MAINTAINER elelphatp "elephantp@elephantp.blog"

RUN mkdir ${DEVKITPRO}/devkitARM && \
    wget https://github.com/devkitPro/buildscripts/releases/download/devkitARM_r50/devkitARM_r50-linux.tar.xz && \
    tar xvJf devkitARM_r50-linux.tar.xz -C ${DEVKITPRO} && \
    git clone --recurse-submodules  https://github.com/switchbrew/libnx && cd libnx && \
    make && make install

RUN apt update && apt install -y python python-pip zip && \
    pip install pycrypto pycryptoplus

ENV DEVKITARM=${DEVKITPRO}/devkitARM

WORKDIR /developer

ENTRYPOINT ["make"]
```
