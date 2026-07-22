# PostgreSQL : Configuration

## Main Files

```text
postgresql.conf
pg_hba.conf
pg_ident.conf
```

## Common Settings

```conf
listen_addresses = 'localhost'
port = 5432
max_connections = 100
shared_buffers = 256MB
log_min_duration_statement = 1000
```

## Inspect and Reload

```sql
SHOW config_file;
SHOW hba_file;
SHOW ALL;
SELECT pg_reload_conf();
```

