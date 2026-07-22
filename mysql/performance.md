# MySQL : Performance

## Query Plans

```sql
EXPLAIN SELECT * FROM orders WHERE user_id = 42;
EXPLAIN ANALYZE SELECT * FROM orders WHERE user_id = 42;
```

## Server Status

```sql
SHOW GLOBAL STATUS;
SHOW GLOBAL STATUS LIKE 'Threads%';
SHOW GLOBAL STATUS LIKE 'Innodb_buffer_pool%';
SHOW PROCESSLIST;
```

## InnoDB and Slow Queries

```sql
SHOW ENGINE INNODB STATUS;
SELECT * FROM performance_schema.events_statements_summary_by_digest
ORDER BY SUM_TIMER_WAIT DESC
LIMIT 10;
```

## Practical Rules

- Index observed query patterns.
- Use explicit transactions for related writes.
- Avoid fetching unused columns and rows.
- Review slow-query data and execution plans.
- Size memory settings from workload measurements and available RAM.
- Validate every tuning change under representative load.
