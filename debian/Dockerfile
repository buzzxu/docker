FROM debian:bookworm-slim

MAINTAINER buzzxu <downloadxu@163.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y wget build-essential pkg-config fontconfig --no-install-recommends && \
	ldconfig /usr/local/lib && \
	rm /etc/localtime && \
    ln -sv /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone && \
    apt-get remove --purge -y wget build-essential pkg-config && \
    apt-get clean && \
    apt-get autoremove -y && \
    apt-get autoclean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/*

ENV TZ Asia/Shanghai
ENV LANG C.UTF-8
