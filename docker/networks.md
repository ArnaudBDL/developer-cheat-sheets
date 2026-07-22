# Docker : Networks

## Manage Networks

```bash
docker network ls
docker network create app-network
docker network inspect app-network
docker network rm app-network
docker network prune
```

## Connect Containers

```bash
docker run -d --name database --network app-network postgres:17-alpine
docker run -d --name application --network app-network my-app
docker network connect app-network existing-container
docker network disconnect app-network existing-container
```

Containers connected to the same user-defined network can communicate using their container names as DNS names.

## Publish Ports

```bash
docker run -d -p 8080:80 nginx
docker run -d -p 127.0.0.1:8080:80 nginx
docker port CONTAINER
```

## Custom Subnet

```bash
docker network create   --driver bridge   --subnet 172.28.0.0/16   --gateway 172.28.0.1   app-network
```

## Inspect Connectivity

```bash
docker inspect -f '{{json .NetworkSettings.Networks}}' CONTAINER
docker exec CONTAINER getent hosts OTHER_CONTAINER
```
