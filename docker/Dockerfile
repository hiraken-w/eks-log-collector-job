FROM public.ecr.aws/amazonlinux/amazonlinux:2.0.20220426.0

ARG CONTAINERD_VERSION="1.4.13-2.amzn2.0.1"
ARG DOCKER_VERSION="20.10.13-2.amzn2"

RUN amazon-linux-extras enable docker \
    && yum install curl awscli iptables conntrack-tools net-tools iproute tar procps lvm2 \
       containerd-${CONTAINERD_VERSION} \
       docker-${DOCKER_VERSION} -y \
    && rm -rf /var/cache/yum/* \
    && yum clean all

ADD https://raw.githubusercontent.com/awslabs/amazon-eks-ami/v20220513/log-collector-script/linux/eks-log-collector.sh /
