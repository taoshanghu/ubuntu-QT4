#####################
# for ubuntu 14.04
# build QT4.8.6 ARM
# taoshanghu
#####################

FROM docker.io/i686/ubuntu:14.04
LABEL maintainer="taoshanghu <taoshanghu@163.com>"
ADD Trolltech.tar.gz /usr/local
ADD x11-dev.tar.gz /usr/local
RUN sed -i "s/archive.ubuntu.com/mirrors.aliyun.com/g" /etc/apt/sources.list && \
        apt update && \
        apt install -y gcc-4.8-arm-linux-gnueabihf g++-4.8-multilib-arm-linux-gnueabihf libphonon-dev zip zlib1g:i386 && \
        ln -s /usr/bin/arm-linux-gnueabihf-gcc-4.8 /usr/bin/arm-linux-gnueabihf-gcc && \
        ln -s /usr/bin/arm-linux-gnueabihf-g++-4.8 /usr/bin/arm-linux-gnueabihf-g++ && \
        echo "/usr/local/x11-dev" >>  /etc/ld.so.conf.d/X11-dev.conf && \
        rm -rf /usr/lib/i386-linux-gnu/libX11.so.6 && \
        ln -s /usr/local/x11-dev/lib/libX11.so.6 /usr/lib/i386-linux-gnu/libX11.so.6 && \
    mkdir /src && \
    chmod 777 /src && \
    rm -rf /var/cache/*
ADD installjammer-1.2.15.tar /usr/local
ENV PATH=/usr/local/Trolltech/Qt-4.8.6/bin:$PATH

WORKDIR /src