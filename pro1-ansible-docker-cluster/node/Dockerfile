# Dockerfile for Ansible Node
FROM ubuntu:latest

# Install Python3, SSH Server, sudo
RUN apt-get update && \
    apt-get install -y python3 python3-pip openssh-server sudo && \
    apt-get clean

# Set root password (example: root)
RUN echo "root:root" | chpasswd

# Configure SSH
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN mkdir /var/run/sshd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]

