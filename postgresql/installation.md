# PostgreSQL : Installation

## Debian and Ubuntu

```bash
sudo apt update
sudo apt install postgresql postgresql-client
sudo systemctl enable --now postgresql
psql --version
```

## Docker

```bash
docker run --name postgresql --detach \
  --publish 127.0.0.1:5432:5432 \
  --env POSTGRES_PASSWORD='change-me' \
  --volume postgresql-data:/var/lib/postgresql/data \
  postgres:latest
```

## Connect

```bash
sudo -u postgres psql
psql --host=127.0.0.1 --username=postgres --dbname=postgres
```

