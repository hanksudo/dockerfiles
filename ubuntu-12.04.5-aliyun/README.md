## Ubuntu 12.04.5 Dockerfile

1. This **Dockerfile** based on Ubuntu 12.04.5, and already done update, upgrade, and preinstall some useful package.
2. Replace packages source to aliyun to speed up download rate in China

### Base Docker Image

 - [hanksudo/ubuntu-12.04.5](https://registry.hub.docker.com/u/hanksudo/ubuntu-12.04.5/)

### Installation

1. Install [Docker](https://docs.docker.com/)
2. Download [automated build](https://registry.hub.docker.com/u/hanksudo/ubuntu-12.04.5-aliyun/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull hanksudo/ubuntu-12.04.5-aliyun`

   (alternatively, you can build an image from Dockerfile: `docker build -t="hanksudo/ubuntu-12.04.5-aliyun" github.com/hanksudo/dockerfiles/ubuntu-12.04.5-aliyun`)

### Usage

```bash
docker run -it --rm hanksudo/ubuntu-12.04.5-aliyun
docker run --rm hanksudo/ubuntu-12.04.5-aliyun /bin/echo "Hello、世界！"
docker run --rm hanksudo/ubuntu-12.04.5-aliyun /bin/bash -c "cat /etc/*-release"
```
