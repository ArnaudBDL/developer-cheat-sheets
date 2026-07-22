# Docker : Images

## List and Inspect

```bash
docker images
docker image ls
docker image ls --digests
docker image inspect IMAGE
docker history IMAGE
```

## Build

```bash
docker build -t my-app:latest .
docker build -t my-app:1.0 -f Dockerfile.production .
docker build --no-cache -t my-app:latest .
docker build --pull -t my-app:latest .
docker build --build-arg APP_ENV=production -t my-app .
```

## Pull, Tag and Push

```bash
docker pull nginx:alpine
docker tag my-app:latest registry.example.com/team/my-app:1.0
docker push registry.example.com/team/my-app:1.0
```

## Remove and Prune

```bash
docker rmi IMAGE
docker image rm IMAGE
docker image prune
docker image prune -a
```

## Save and Load

```bash
docker save -o image.tar my-app:1.0
docker load -i image.tar
```
