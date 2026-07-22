# SQLite : Performance

## Query Plans

```sql
EXPLAIN QUERY PLAN
SELECT * FROM orders WHERE user_id = 42;
```

## Statistics and Optimization

```sql
ANALYZE;
PRAGMA optimize;
```

## Write-Ahead Logging

```sql
PRAGMA journal_mode = WAL;
PRAGMA synchronous = NORMAL;
PRAGMA busy_timeout = 5000;
```

Choose durability-related pragmas according to workload and recovery requirements. Do not copy tuning values without validating their consequences.

## Cache and Temporary Storage

```sql
PRAGMA cache_size = -65536;
PRAGMA temp_store = MEMORY;
PRAGMA mmap_size = 268435456;
```

## Database Size

```sql
PRAGMA page_size;
PRAGMA page_count;
PRAGMA freelist_count;
VACUUM;
```

## Practical Rules

- Group related writes inside explicit transactions.
- Add indexes for observed query patterns, not every column.
- Inspect plans after schema or query changes.
- Keep transactions short when multiple connections write.
- Use prepared statements and reuse connections appropriately.
- Measure before and after each tuning change.
