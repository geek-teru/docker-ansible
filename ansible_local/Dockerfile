# Amazon Linux 2
FROM amazonlinux:2

RUN yum install -y git iputils
RUN amazon-linux-extras enable ansible2
RUN yum install -y ansible

COPY ./ssh_config /root/.ssh/config
RUN chmod 644 /root/.ssh/config

COPY ./infra.rsa /root/.ssh/infra.rsa
RUN chmod 600 /root/.ssh/infra.rsa
