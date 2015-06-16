## Ubuntu 12.04.5 Dockerfile

This **Dockerfile** based on Ubuntu 12.04.5, and already done update, upgrade, and preinstall some useful package.

### Base Docker Image

 - [ubuntu official repo](https://registry.hub.docker.com/_/ubuntu/)

### Installation

1. Install [Docker](https://docs.docker.com/)
2. Download [automated build](https://registry.hub.docker.com/u/hanksudo/ubuntu-12.04.5/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull hanksudo/ubuntu-12.04.5`

   (alternatively, you can build an image from Dockerfile: `docker build -t="hanksudo/ubuntu-12.04.5" github.com/hanksudo/dockerfiles/ubuntu-12.04.5`)

### Usage

```bash
docker run -it --rm hanksudo/ubuntu-12.04.5
docker run --rm hanksudo/ubuntu-12.04.5 /bin/echo "Hello、世界！"
docker run --rm hanksudo/ubuntu-12.04.5 /bin/bash -c "cat /etc/*-release"
```
