# Docker : Troubleshooting

## General Diagnostics

```bash
docker version
docker info
docker system df
docker ps -a
docker events --since 30m
```

## Container Does Not Start

```bash
docker ps -a
docker logs CONTAINER
docker inspect CONTAINER
docker inspect -f '{{.State.Status}} {{.State.ExitCode}} {{.State.Error}}' CONTAINER
docker start -a CONTAINER
```

## Shell Access

```bash
docker exec -it CONTAINER sh
docker exec -it CONTAINER bash
docker run --rm -it --entrypoint sh IMAGE
```

## Ports and Networking

```bash
docker port CONTAINER
docker network ls
docker network inspect NETWORK
docker inspect -f '{{json .NetworkSettings.Networks}}' CONTAINER
lsof -i :8080
```

## Disk Usage

```bash
docker system df
docker system df -v
docker image prune
docker container prune
docker volume prune
docker builder prune
docker system prune
```

## Compose Diagnostics

```bash
docker compose config
docker compose ps -a
docker compose logs --tail 200
docker compose events
docker compose build --no-cache SERVICE
```

## Reset with Caution

The following commands remove unused objects. Verify persistent data before running them.

```bash
docker compose down -v
docker system prune -a --volumes
```
