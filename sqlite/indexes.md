# SQLite : Indexes

## Create Indexes

```sql
CREATE INDEX idx_users_created_at
ON users(created_at);

CREATE UNIQUE INDEX idx_users_email
ON users(email);
```

## Composite Index

```sql
CREATE INDEX idx_orders_user_created
ON orders(user_id, created_at DESC);
```

## Partial Index

```sql
CREATE INDEX idx_users_active_email
ON users(email)
WHERE active = 1;
```

## Expression Index

```sql
CREATE INDEX idx_users_lower_email
ON users(lower(email));
```

## Inspect Query Plans

```sql
EXPLAIN QUERY PLAN
SELECT * FROM orders WHERE user_id = 42;

PRAGMA index_list(orders);
PRAGMA index_info(idx_orders_user_created);
```

## Maintenance

```sql
ANALYZE;
PRAGMA optimize;
REINDEX idx_orders_user_created;
DROP INDEX IF EXISTS idx_orders_user_created;
```
