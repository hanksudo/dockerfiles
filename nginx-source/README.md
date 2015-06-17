## nginx Dockerfile (compile from source)

nginx web server compile from source

### Base Docker Image

 - [hanksudo/ubuntu-12.04.5](https://registry.hub.docker.com/u/hanksudo/ubuntu-12.04.5/)

### Installation

1. Install [Docker](https://docs.docker.com/)
2. Download [automated build](https://registry.hub.docker.com/u/hanksudo/nginx-source/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull hanksudo/nginx-source`

3. alternatively, you can build an image from Dockerfile, clone this repo then: 
4. 
```bash
cd nginx-source
docker build -t="hanksudo/nginx-source" .
```

### Usage

```bash
docker run -d -p 9300:80 hanksudo/nginx-source
docker run -d -p 9300:80 -v ${PWD}/html:/opt/nginx/html hanksudo/nginx-source
docker run --name=nginx -d -p 9300:80 -v ${PWD}/html:/opt/nginx/html hanksudo/nginx-source
docker logs -f nginx # follow request and error log
```
