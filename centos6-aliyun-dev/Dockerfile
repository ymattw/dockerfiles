# Populate a centos 6.5 "dev" box using aliyun mirrored yum repo
FROM ymattw/centos6-aliyun:latest
MAINTAINER Matthew Wang
RUN yum groupinstall -y "Development tools"
RUN yum install -y wget tar file vim nc bind-utils
