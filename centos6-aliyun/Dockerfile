# Populate a centos 6.5 "dev" box using aliyun mirrored yum repo
FROM centos:6
MAINTAINER Matthew Wang
VOLUME /home /root
RUN sed -i 's/enabled=1/enabled=0/' /etc/yum/pluginconf.d/fastestmirror.conf
RUN rm -f /etc/yum.repos.d/*
RUN curl -sSL http://mirrors.aliyun.com/repo/Centos-6.repo > /etc/yum.repos.d/aliyun.repo
