# SQLite : Queries

## Insert Data

```sql
INSERT INTO users (email, name)
VALUES ('user@example.com', 'User');

INSERT INTO users (email, name)
VALUES
    ('alice@example.com', 'Alice'),
    ('bob@example.com', 'Bob');
```

## Select Data

```sql
SELECT id, email, name
FROM users
WHERE active = 1
ORDER BY created_at DESC
LIMIT 20 OFFSET 0;
```

## Update and Delete

```sql
UPDATE users
SET active = 0
WHERE id = 42;

DELETE FROM users
WHERE id = 42;
```

## Join

```sql
SELECT users.name, orders.id, orders.total
FROM users
JOIN orders ON orders.user_id = users.id
WHERE orders.total > 100;
```

## Aggregate

```sql
SELECT user_id, COUNT(*) AS order_count, SUM(total) AS total_amount
FROM orders
GROUP BY user_id
HAVING COUNT(*) >= 2;
```

## Upsert

```sql
INSERT INTO settings (name, value)
VALUES ('theme', 'dark')
ON CONFLICT(name) DO UPDATE
SET value = excluded.value;
```

## Common Table Expression

```sql
WITH active_users AS (
    SELECT id, name
    FROM users
    WHERE active = 1
)
SELECT * FROM active_users;
```
