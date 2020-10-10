FROM debian:buster-slim

LABEL MAINTAINER buzzxu <downloadxu@163.com>

ENV DEBIAN_FRONTEND noninteractive

RUN echo \
    deb http://mirrors.163.com/debian/ buster main non-free contrib \
    deb http://mirrors.163.com/debian/ buster-updates main non-free contrib \
    deb http://mirrors.163.com/debian/ buster-backports main non-free contrib \
    deb http://mirrors.163.com/debian-security/ buster/updates main non-free contrib \
    deb-src http://mirrors.163.com/debian/ buster main non-free contrib \
    deb-src http://mirrors.163.com/debian/ buster-updates main non-free contrib \
    deb-src http://mirrors.163.com/debian/ buster-backports main non-free contrib \
    deb-src http://mirrors.163.com/debian-security/ buster/updates main non-free contrib \
    > /etc/apt/sources.list

RUN rm -rf /var/lib/apt/lists/* && \  
    apt-get clean && \
    apt-get update -qq && \ 
    apt-get upgrade -y && \
    apt-get install -qq -y --no-install-recommends openssl ca-certificates && \
    update-ca-certificates && \
    rm /etc/localtime && \
    ln -sv /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \ 
    echo "Asia/Shanghai" > /etc/timezone && \
    apt-get autoclean && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/* 

ENV TZ=Asia/Shanghai
ENV LANG='C.UTF-8' LC_ALL='C.UTF-8'
