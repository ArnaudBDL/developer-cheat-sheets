# Docker Compose Template

Use this template to create a project `compose.yaml` or `docker-compose.yml` file.

## Template

```yaml
name: {{PROJECT_SLUG}}

services:
  application:
    build:
      context: .
      dockerfile: Dockerfile
      target: {{DOCKER_TARGET}}
    environment:
      APP_ENV: ${APP_ENV:-development}
      APP_PORT: ${APP_PORT:-8080}
      DATABASE_URL: ${DATABASE_URL:-postgresql://application:application@database:5432/application}
    ports:
      - "${APP_PORT:-8080}:8080"
    volumes:
      - .:/workspace
      - application-cache:/workspace/.cache
    depends_on:
      database:
        condition: service_healthy
    healthcheck:
      test: ["CMD", "{{HEALTHCHECK_COMMAND}}"]
      interval: 10s
      timeout: 5s
      retries: 5
      start_period: 20s
    restart: unless-stopped
    networks:
      - application-network

  database:
    image: postgres:${POSTGRES_VERSION:-17-alpine}
    environment:
      POSTGRES_DB: ${POSTGRES_DB:-application}
      POSTGRES_USER: ${POSTGRES_USER:-application}
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD:-application}
    volumes:
      - database-data:/var/lib/postgresql/data
    healthcheck:
      test:
        - CMD-SHELL
        - pg_isready -U "$${POSTGRES_USER}" -d "$${POSTGRES_DB}"
      interval: 10s
      timeout: 5s
      retries: 5
      start_period: 10s
    restart: unless-stopped
    networks:
      - application-network

volumes:
  application-cache:
  database-data:

networks:
  application-network:
    driver: bridge
```

## Minimal `.env.example`

```dotenv
APP_ENV=development
APP_PORT=8080
POSTGRES_VERSION=17-alpine
POSTGRES_DB=application
POSTGRES_USER=application
POSTGRES_PASSWORD=application
DATABASE_URL=postgresql://application:application@database:5432/application
```

## Required Replacements

```text
{{PROJECT_SLUG}}
{{DOCKER_TARGET}}
{{HEALTHCHECK_COMMAND}}
```

## Validation

```bash
docker compose config
docker compose build
docker compose up --wait
docker compose ps
docker compose logs application
docker compose down
```

## Rules

- Prefer `compose.yaml` for new projects unless the repository convention requires another name.
- Keep service names stable because they are internal DNS names on the Compose network.
- Pin production image versions instead of relying on `latest`.
- Never place production credentials directly in the Compose file.
- Commit `.env.example`, but exclude `.env` and secret files.
- Add a health check for every service used by `depends_on` conditions.
- Persist only data that must survive container recreation.
- Use named volumes for service data and bind mounts only when host access is required.
- Do not publish database ports unless host access is necessary.
- Use separate development and production overrides when their runtime behavior differs.
- Remove the database service if the application does not require PostgreSQL.
- Replace default development credentials before any shared or production deployment.
