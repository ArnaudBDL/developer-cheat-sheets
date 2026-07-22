# SQLite : Views

## Create a View

```sql
CREATE VIEW active_users AS
SELECT id, email, name, created_at
FROM users
WHERE active = 1;
```

## Query a View

```sql
SELECT *
FROM active_users
ORDER BY created_at DESC;
```

## Aggregate View

```sql
CREATE VIEW user_order_totals AS
SELECT
    users.id AS user_id,
    users.name,
    COUNT(orders.id) AS order_count,
    COALESCE(SUM(orders.total), 0) AS total_amount
FROM users
LEFT JOIN orders ON orders.user_id = users.id
GROUP BY users.id, users.name;
```

## Inspect and Drop

```sql
SELECT name, sql
FROM sqlite_schema
WHERE type = 'view';

DROP VIEW IF EXISTS active_users;
```

SQLite views are read-only by default. `INSTEAD OF` triggers can implement controlled write behavior on a view.
