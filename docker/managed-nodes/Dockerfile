FROM ubuntu:latest

RUN apt-get update && \
    apt-get install -y openssh-server

RUN mkdir /var/run/sshd

RUN sed -ri 's/^#PasswordAuthentication yes/PasswordAuthentication no/' /etc/ssh/sshd_config \
 && echo 'root:password' | chpasswd

COPY managed-nodes/.ssh/ /root/.ssh/
RUN chmod 700 /root/.ssh
RUN chmod 644 /root/.ssh/authorized_keys

WORKDIR /root

EXPOSE 22
