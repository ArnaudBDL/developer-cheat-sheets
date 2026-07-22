# Docker : Volumes

## Manage Volumes

```bash
docker volume create app-data
docker volume ls
docker volume inspect app-data
docker volume rm app-data
docker volume prune
```

## Named Volume

```bash
docker run -d --name database   -v database-data:/var/lib/postgresql/data   postgres:17-alpine
```

## Bind Mount

```bash
docker run --rm   --mount type=bind,source="$(pwd)",target=/app   -w /app   node:22-alpine npm test
```

## Read-Only Mount

```bash
docker run --rm   --mount type=bind,source="$(pwd)/config",target=/app/config,readonly   IMAGE
```

## Backup and Restore

```bash
# Backup
docker run --rm   -v app-data:/data   -v "$(pwd)":/backup   alpine tar czf /backup/app-data.tar.gz -C /data .

# Restore
docker run --rm   -v app-data:/data   -v "$(pwd)":/backup   alpine tar xzf /backup/app-data.tar.gz -C /data
```
