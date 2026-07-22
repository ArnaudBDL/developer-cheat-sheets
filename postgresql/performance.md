# PostgreSQL : Performance

## Plans

```sql
EXPLAIN (ANALYZE, BUFFERS, VERBOSE)
SELECT * FROM orders WHERE user_id = 42;
```

## Activity

```sql
SELECT pid, usename, state, wait_event_type, query FROM pg_stat_activity;
SELECT * FROM pg_stat_user_tables;
SELECT * FROM pg_stat_user_indexes;
```

## Maintenance

```sql
VACUUM (ANALYZE) users;
ANALYZE orders;
REINDEX TABLE users;
```

## Rules

```text
Index observed query patterns, keep statistics current, avoid long idle transactions, inspect locks and wait events, and validate tuning changes under representative load.
```

