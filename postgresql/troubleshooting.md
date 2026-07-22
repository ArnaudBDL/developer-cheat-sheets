# PostgreSQL : Troubleshooting

## Connectivity

```bash
pg_isready --host=HOST --port=5432
psql --host=HOST --username=USER --dbname=DB
ss -lntp | grep 5432
```

## Service and Logs

```bash
systemctl status postgresql
journalctl -u postgresql -n 200
tail -f /var/log/postgresql/postgresql-*.log
```

## Diagnostics

```sql
SELECT version();
SELECT * FROM pg_stat_activity;
SELECT * FROM pg_locks WHERE NOT granted;
SELECT pg_size_pretty(pg_database_size(current_database()));
```

## Common Problems

```text
Connection refused: check service, listen_addresses, port and firewall.
Authentication failed: check role, password, database and pg_hba.conf order.
Too many connections: inspect pg_stat_activity and application pooling.
Deadlock or lock timeout: inspect pg_locks, transaction duration and access order.
Disk full: check data, WAL, logs, temporary files and filesystem capacity.
```

