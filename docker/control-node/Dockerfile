FROM ubuntu:latest

RUN apt-get update && \
    apt-get install -y openssh-client && \
    apt-get install -y neovim && \
    apt-get install -y python3-pip && \
    pip3 install ansible

COPY control-node/.ssh/ /root/.ssh/
RUN chmod 700 /root/.ssh
RUN chmod 600 /root/.ssh/managed-node-key

WORKDIR /root
