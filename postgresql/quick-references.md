# PostgreSQL : Quick References

## CLI

```bash
psql -U postgres
psql -U USER -d DATABASE
\l
\c DATABASE
\dt
\d TABLE
\q
```

## Database

```sql
CREATE DATABASE app;
CREATE USER app WITH PASSWORD 'password';
GRANT ALL PRIVILEGES ON DATABASE app TO app;
```

## Queries

```sql
SELECT * FROM users ORDER BY created_at DESC LIMIT 20;
EXPLAIN ANALYZE SELECT * FROM users WHERE email = $1;
CREATE INDEX idx_users_email ON users (email);
```

## Backup

```bash
pg_dump -Fc DATABASE > backup.dump
pg_restore -d DATABASE backup.dump
```
