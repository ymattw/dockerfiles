# Populate a centos 7 with aliyun mirror integrated
FROM centos:7
MAINTAINER Matthew Wang
RUN sed -i 's/enabled=1/enabled=0/' /etc/yum/pluginconf.d/fastestmirror.conf
RUN rm -f /etc/yum.repos.d/*
RUN curl -sSL http://mirrors.aliyun.com/repo/Centos-7.repo > /etc/yum.repos.d/aliyun.repo
