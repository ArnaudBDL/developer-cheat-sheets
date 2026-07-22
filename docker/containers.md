# Docker : Containers

## Run Containers

```bash
docker run IMAGE
docker run --name my-container IMAGE
docker run -d --name my-container IMAGE
docker run --rm IMAGE
docker run -it --rm IMAGE sh
docker run -d -p 8080:80 IMAGE
docker run -d -e APP_ENV=production IMAGE
```

## List Containers

```bash
docker ps
docker ps -a
docker ps -q
docker ps --filter status=running
docker ps --format 'table {{.Names}}	{{.Image}}	{{.Status}}	{{.Ports}}'
```

## Lifecycle

```bash
docker start CONTAINER
docker stop CONTAINER
docker stop -t 30 CONTAINER
docker restart CONTAINER
docker pause CONTAINER
docker unpause CONTAINER
docker kill CONTAINER
docker rm CONTAINER
docker rm -f CONTAINER
```

## Execute Commands

```bash
docker exec CONTAINER COMMAND
docker exec -it CONTAINER sh
docker exec -it CONTAINER bash
docker exec -u root -it CONTAINER sh
```

## Inspect and Copy

```bash
docker inspect CONTAINER
docker top CONTAINER
docker stats CONTAINER
docker port CONTAINER
docker diff CONTAINER
docker cp local-file CONTAINER:/path/
docker cp CONTAINER:/path/file local-file
```
