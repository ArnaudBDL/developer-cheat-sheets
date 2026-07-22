# PostgreSQL : Queries

## CRUD

```sql
INSERT INTO users (email, name) VALUES ('user@example.com', 'User') RETURNING *;
SELECT id, email, name FROM users WHERE active ORDER BY created_at DESC LIMIT 20;
UPDATE users SET active = FALSE WHERE id = 42 RETURNING *;
DELETE FROM users WHERE id = 42 RETURNING *;
```

## Join and Aggregate

```sql
SELECT u.id, u.name, count(o.id) AS order_count, coalesce(sum(o.total), 0) AS total
FROM users u LEFT JOIN orders o ON o.user_id = u.id
GROUP BY u.id, u.name HAVING count(o.id) >= 2;
```

## Upsert

```sql
INSERT INTO settings (name, value) VALUES ('theme', 'dark')
ON CONFLICT (name) DO UPDATE SET value = EXCLUDED.value;
```

