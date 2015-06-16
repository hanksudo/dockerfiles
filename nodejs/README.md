## Node.js Dockerfile

1. Use node.js or io.js.
2. use [n](https://github.com/tj/n) node version management to install and execute nodejs with different version.

### Base Docker Image

 - [hanksudo/ubuntu-12.04.5](https://registry.hub.docker.com/u/hanksudo/ubuntu-12.04.5/)

### Installation

1. Install [Docker](https://docs.docker.com/)
2. Download [automated build](https://registry.hub.docker.com/u/hanksudo/nodejs) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull hanksudo/nodejs`

3. alternatively, you can build an image from Dockerfile, clone this repo then: `docker build -t="hanksudo/nodejs" ./nodejs`)

### Usage

```bash
docker run --rm hanksudo/nodejs
docker run --rm hanksudo/nodejs node -v

# swtich nodejs version
docker run --rm hanksudo/nodejs /bin/bash n 0.11.1
docker run --rm hanksudo/nodejs /bin/bash n io stable

# execute js file
docker run -v ${PWD}/src:/root/src --rm hanksudo/nodejs node src/app.js
docker run -v ${PWD}/src:/root/src --rm hanksudo/nodejs n 0.11.1 && n use 0.11.1 src/app.js
docker run -v ${PWD}/src:/root/src --rm hanksudo/nodejs n io 2.2.1 && iojs -v
docker run -v ${PWD}/src:/root/src --rm hanksudo/nodejs n io 2.2.1 && n io use 2.2.1 src/app.js
```
