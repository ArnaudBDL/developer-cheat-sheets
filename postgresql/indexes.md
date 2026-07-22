# PostgreSQL : Indexes

## Create

```sql
CREATE INDEX idx_users_created_at ON users (created_at DESC);
CREATE UNIQUE INDEX uk_users_email_lower ON users (lower(email));
CREATE INDEX idx_active_users ON users (email) WHERE active;
CREATE INDEX idx_records_metadata ON records USING GIN (metadata);
```

## Inspect Plans

```sql
\di+
EXPLAIN SELECT * FROM users WHERE email = 'user@example.com';
EXPLAIN (ANALYZE, BUFFERS) SELECT * FROM orders WHERE user_id = 42;
```

## Maintain

```sql
REINDEX INDEX idx_users_created_at;
DROP INDEX IF EXISTS idx_users_created_at;
```

