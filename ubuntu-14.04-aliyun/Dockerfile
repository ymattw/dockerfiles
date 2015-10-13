# Populate a ubuntu:14.04 image with aliyun mirror settled, see also
# http://mirrors.aliyun.com/help/ubuntu
#
FROM ubuntu:14.04
RUN echo '# Alibaba ubuntu mirror, see http://mirrors.aliyun.com/help/ubuntu' > /etc/apt/sources.list
RUN echo 'deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb-src http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb-src http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb-src http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb-src http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse' >> /etc/apt/sources.list
RUN echo 'deb-src http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse' >> /etc/apt/sources.list
RUN apt-get update
