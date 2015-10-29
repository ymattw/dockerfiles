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
ENV __myke_server_dir /export/servers
ENV __myke_kafka_url http://mirrors.aliyun.com/apache/kafka/0.8.2.1/kafka_2.11-0.8.2.1.tgz
ENV __myke_kafka_dir ${__myke_server_dir}/kafka
RUN curl --location ${__myke_kafka_url} > /tmp/kafka.tgz && \
    mkdir -p ${__myke_kafka_dir} && \
    tar -C ${__myke_kafka_dir} --strip-components=1 -xzf /tmp/kafka.tgz && \
    rm -f /tmp/kafka.tgz

# Install elasticsearch
ENV __myke_es_repo_file /etc/yum.repos.d/es.repo
RUN echo '[elasticsearch-1.7]' > ${__myke_es_repo_file} && \
    echo 'name=Elasticsearch repository for 1.7.x packages' >> ${__myke_es_repo_file} && \
    echo 'baseurl=http://packages.elastic.co/elasticsearch/1.7/centos' >> ${__myke_es_repo_file} && \
    echo 'gpgcheck=1' >> ${__myke_es_repo_file} && \
    echo 'gpgkey=http://packages.elastic.co/GPG-KEY-elasticsearch' >> ${__myke_es_repo_file} && \
    echo 'enabled=1' >> ${__myke_es_repo_file} && \
    yum install -y elasticsearch && \
    rm -f ${__myke_es_repo_file}
