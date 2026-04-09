FROM ubuntu:22.04

RUN apt update && \
    apt install -y \
    openssh-serve \
    curl \
    git \
    sudo \
    docker.io \
    maven \
    openjdk-17-jdk
RUN mkdir /var/run/sshd

RUN useradd -m -s /bin/bash jenkins && \
    usermod -aG sudo jenkins && \
    usermod -aG docker jenkins &&\ 
    mkdir /home/jenkins/.ssh && \
    chown -R jenkins:jenkins /home/jenkins/.ssh && \
    chmod 700 /home/jenkins/.ssh
RUN chmod 666 /var/run/docker.sock || true

EXPOSE 22 

CMD ["/usr/sbin/sshd", "-D"]
