# Docker : Docker Compose

## Compose File

```yaml
services:
  app:
    build:
      context: .
    ports:
      - "8080:3000"
    environment:
      APP_ENV: production
    depends_on:
      database:
        condition: service_healthy
    restart: unless-stopped

  database:
    image: postgres:17-alpine
    environment:
      POSTGRES_DB: app
      POSTGRES_USER: app
      POSTGRES_PASSWORD: change-me
    volumes:
      - database-data:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U app -d app"]
      interval: 10s
      timeout: 5s
      retries: 5

volumes:
  database-data:
```

## Lifecycle

```bash
docker compose up
docker compose up -d
docker compose up -d --build
docker compose stop
docker compose start
docker compose restart
docker compose down
docker compose down -v
```

## Inspection

```bash
docker compose ps
docker compose logs
docker compose logs -f SERVICE
docker compose top
docker compose config
docker compose images
```

## Services

```bash
docker compose build SERVICE
docker compose pull
docker compose exec SERVICE sh
docker compose run --rm SERVICE COMMAND
docker compose scale SERVICE=3
```

## Profiles and Files

```bash
docker compose --profile debug up -d
docker compose -f compose.yaml -f compose.production.yaml up -d
```
