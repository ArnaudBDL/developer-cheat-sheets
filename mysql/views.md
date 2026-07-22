# MySQL : Views

## Create and Query

```sql
CREATE VIEW active_users AS
SELECT id, email, name, created_at
FROM users
WHERE active = TRUE;

SELECT * FROM active_users ORDER BY created_at DESC;
```

## Replace and Inspect

```sql
CREATE OR REPLACE VIEW active_users AS
SELECT id, email, name
FROM users
WHERE active = TRUE;

SHOW CREATE VIEW active_users;
SHOW FULL TABLES WHERE table_type = 'VIEW';
```

## Drop

```sql
DROP VIEW IF EXISTS active_users;
```
