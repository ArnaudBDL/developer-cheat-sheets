# MySQL : Queries

## Insert

```sql
INSERT INTO users (email, name)
VALUES ('user@example.com', 'User');

INSERT INTO users (email, name)
VALUES ('alice@example.com', 'Alice'),
       ('bob@example.com', 'Bob');
```

## Select

```sql
SELECT id, email, name
FROM users
WHERE active = TRUE
ORDER BY created_at DESC
LIMIT 20 OFFSET 0;
```

## Join and Aggregate

```sql
SELECT users.id, users.name, COUNT(orders.id) AS order_count,
       COALESCE(SUM(orders.total), 0) AS total_amount
FROM users
LEFT JOIN orders ON orders.user_id = users.id
GROUP BY users.id, users.name
HAVING COUNT(orders.id) >= 2;
```

## Update and Delete

```sql
UPDATE users SET active = FALSE WHERE id = 42;
DELETE FROM users WHERE id = 42;
```

## Upsert

```sql
INSERT INTO settings (name, value)
VALUES ('theme', 'dark') AS new
ON DUPLICATE KEY UPDATE value = new.value;
```
