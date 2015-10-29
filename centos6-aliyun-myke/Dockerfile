# Populate a centos 6.5 box with
#
#   - aliyun mirrored yum repo
#   - mysql-server
#   - java (1.7.0-openjdk)
#   - kafka (2.11-0.8.2.1)
#   - elasticsearch (1.7.x)
#
FROM ymattw/centos6-aliyun-mysqld:latest
MAINTAINER Matthew Wang

# Install dependencies
RUN yum install -y tar which java-1.7.0-openjdk

# Install kafka
ENV KAFKA_TGZ_URL http://mirrors.aliyun.com/apache/kafka/0.8.2.1/kafka_2.11-0.8.2.1.tgz
ENV KAFKA_DIR /opt/kafka
ENV KAFKA_TMP_TGZ /tmp/kafka.tgz
RUN curl --location $KAFKA_TGZ_URL > $KAFKA_TMP_TGZ && \
    mkdir -p $KAFKA_DIR && \
    tar -C $KAFKA_DIR --strip-components=1 -xzf $KAFKA_TMP_TGZ && \
    rm -f $KAFKA_TMP_TGZ

# Install elasticsearch
ENV ES_REPO_FILE /etc/yum.repos.d/es.repo
RUN echo '[elasticsearch-1.7]' > $ES_REPO_FILE && \
    echo 'name=Elasticsearch repository for 1.7.x packages' >> $ES_REPO_FILE && \
    echo 'baseurl=http://packages.elastic.co/elasticsearch/1.7/centos' >> $ES_REPO_FILE && \
    echo 'gpgcheck=1' >> $ES_REPO_FILE && \
    echo 'gpgkey=http://packages.elastic.co/GPG-KEY-elasticsearch' >> $ES_REPO_FILE && \
    echo 'enabled=1' >> $ES_REPO_FILE && \
    yum install -y elasticsearch && \
    rm -f $ES_REPO_FILE
