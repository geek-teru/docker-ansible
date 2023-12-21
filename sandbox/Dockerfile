# Amazon Linux release 2023 (Amazon Linux)
FROM amazonlinux:2

RUN yum install -y openssh-clients openssh-server passwd sudo git

RUN groupadd infra
RUN useradd infra -g infra

# infraユーザーの鍵を配置
RUN mkdir -p /home/infra/.ssh

COPY ./infra_rsa.pub /home/infra/.ssh/id_rsa.pub
RUN chmod 600 /home/infra/.ssh/id_rsa.pub
RUN cat /home/infra/.ssh/id_rsa.pub >> /home/infra/.ssh/authorized_keys

# ディレクトリの権限設定
RUN chmod 600 /home/infra/.ssh/authorized_keys
RUN chmod 700 /home/infra/.ssh
RUN chown -R infra:infra /home/infra/.ssh

# sudo設定
RUN echo "infra        ALL=(ALL)       NOPASSWD: ALL" >> /etc/sudoers

# SSHポート許可
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
CMD ["/usr/sbin/init"]