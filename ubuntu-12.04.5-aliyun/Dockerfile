# hanksudo/ubuntu-12.04.5-aliyun

# Pull base image
FROM ubuntu:12.04.5
MAINTAINER Hank Wang <drapho@gmail.com>

RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
COPY ./sources.list-aliyun /etc/apt/sources.list

# Install
RUN \
    apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y build-essential && \
    apt-get install -y software-properties-common && \
    apt-get install -y curl wget git unzip htop man vim

# clean up
RUN rm -rf /var/lib/apt/lists/*

# Define working directory.
# WORKDIR /root

# Default command
CMD ["bash"]
