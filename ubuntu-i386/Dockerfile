#####################
# for ubuntu 14.04
# build QT4.8.6 
# taoshanghu
#####################

FROM docker.io/i686/ubuntu:14.04
LABEL maintainer="taoshanghu <taoshanghu@163.com>"
COPY localfile/installjammer /usr/local/installjammer

RUN sed -i "s/archive.ubuntu.com/mirrors.aliyun.com/g" /etc/apt/sources.list && \
    apt update && \
    apt install -y build-essential checkinstall qt4-default libphonon-dev zip zlib1g:i386 && \
    mkdir /src && \
    chmod 777 /src && \
    rm -rf /var/cache/* && \
    chmod 755 /usr/local/installjammer/installjammer

ENV SYSTEMBITS=x86
WORKDIR /src