FROM centos:8

RUN sed -i -e 's/^mirrorlist/#mirrorlist/g' -e 's/^#baseurl=http:\/\/mirror/baseurl=http:\/\/vault/g' /etc/yum.repos.d/CentOS-*repo

RUN yum update -y && \
    yum install -y openssh-server && \
    yum install -y python39

RUN sed -ri 's/^#PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config \
 && echo 'root:password' | chpasswd

COPY managed-nodes/.ssh/ /root/.ssh/
RUN chmod 700 /root/.ssh
RUN chmod 644 /root/.ssh/authorized_keys

WORKDIR /root

CMD systemctl start sshd

EXPOSE 22
