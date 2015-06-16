# Dockerfiles

## run

```bash
docker run -v -it --rm hanksudo/ubuntu-12.04.5:latest
docker run -v ${PWD}:/root -it --rm hanksudo/ubuntu-12.04.5:latest
```

## or build your own

```bash
docker build -t 'hanksudo/ubuntu-12.04.5'
```
