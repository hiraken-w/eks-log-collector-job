FROM amazonlinux:2.0.20201218.1

RUN yum install curl awscli iptables conntrack-tools net-tools iproute tar procps lvm2 -y \
    && rm -rf /var/cache/yum/* \
    && yum clean all

ARG DOCKER_VERSION="19.03.8"
RUN curl -O  https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz \
    && tar xfz  docker-${DOCKER_VERSION}.tgz \
    && mv ./docker/docker /usr/bin \
    && rm -rf docker-${DOCKER_VERSION}.tgz docker

ADD https://raw.githubusercontent.com/awslabs/amazon-eks-ami/2e0954b1cbe4a3321e7391cd1075d64eacda1f91/log-collector-script/linux/eks-log-collector.sh /
