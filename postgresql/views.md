# PostgreSQL : Views

## Create

```sql
CREATE VIEW active_users AS
SELECT id, email, name FROM users WHERE active;

CREATE MATERIALIZED VIEW user_totals AS
SELECT user_id, count(*) AS orders, sum(total) AS total FROM orders GROUP BY user_id;
```

## Manage

```sql
SELECT * FROM active_users;
REFRESH MATERIALIZED VIEW user_totals;
\dv+
\dm+
DROP VIEW IF EXISTS active_users;
```

