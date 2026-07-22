# Docker : Logs

## Read Logs

```bash
docker logs CONTAINER
docker logs -f CONTAINER
docker logs --tail 100 CONTAINER
docker logs --since 30m CONTAINER
docker logs --since 2026-07-21T20:00:00 CONTAINER
docker logs --timestamps CONTAINER
```

## Compose Logs

```bash
docker compose logs
docker compose logs -f
docker compose logs --tail 100 SERVICE
docker compose logs --since 30m SERVICE
```

## Logging Driver

```bash
docker info --format '{{.LoggingDriver}}'
docker inspect -f '{{.HostConfig.LogConfig.Type}}' CONTAINER
```

```yaml
services:
  app:
    image: my-app
    logging:
      driver: json-file
      options:
        max-size: "10m"
        max-file: "3"
```

## Events

```bash
docker events
docker events --since 30m
docker events --filter container=CONTAINER
```
