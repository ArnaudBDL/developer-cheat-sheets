# MongoDB : Installation

## Install with Docker

```bash
docker run --name mongodb --detach \
  --publish 127.0.0.1:27017:27017 \
  --volume mongodb-data:/data/db \
  mongo:latest
```

## Verify

```bash
mongod --version
mongosh --version
mongosh "mongodb://127.0.0.1:27017"
docker logs mongodb
```

