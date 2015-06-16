# Pull base image
FROM ubuntu:12.04.5

# Install
RUN \
    sed -i 's/# \(.multiverse$\)/\1/g' /etc/apt/sources.list && \
    apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y build-essential && \
    apt-get install -y software-properties-common && \
    apt-get install -y curl wget git unzip htop man vim && \
    rm -rf /var/lib/apt/lists/*

# Define working directory.
WORKDIR /root

# Default command
CMD ["bash"]
