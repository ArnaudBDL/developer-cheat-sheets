# MySQL : Indexes

## Create Indexes

```sql
CREATE INDEX idx_users_created_at ON users(created_at);
CREATE UNIQUE INDEX uk_users_email ON users(email);
CREATE INDEX idx_orders_user_created ON orders(user_id, created_at DESC);
```

## Full-Text Index

```sql
CREATE FULLTEXT INDEX ft_articles_content
ON articles(title, content);
```

## Inspect Plans

```sql
SHOW INDEX FROM users;
EXPLAIN SELECT * FROM users WHERE email = 'user@example.com';
EXPLAIN ANALYZE SELECT * FROM orders WHERE user_id = 42;
```

## Drop an Index

```sql
DROP INDEX idx_users_created_at ON users;
```
