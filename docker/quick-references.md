# Docker : Quick References

## Lifecycle

```bash
docker build -t my-app .
docker run -d --name my-app -p 8080:80 my-app
docker stop my-app
docker start my-app
docker restart my-app
docker rm my-app
```

## Inspection

```bash
docker ps -a
docker images
docker logs -f my-app
docker exec -it my-app sh
docker inspect my-app
docker stats
```

## Cleanup

```bash
docker image prune
docker container prune
docker volume prune
docker network prune
docker system prune -a
```

## Docker Compose

```bash
docker compose up -d
docker compose ps
docker compose logs -f
docker compose restart
docker compose down
```
