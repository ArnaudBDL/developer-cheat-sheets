# SQLite : Triggers

## After Insert Trigger

```sql
CREATE TRIGGER users_after_insert
AFTER INSERT ON users
BEGIN
    INSERT INTO audit_log (event, entity_id, created_at)
    VALUES ('user.created', NEW.id, CURRENT_TIMESTAMP);
END;
```

## Before Update Trigger

```sql
CREATE TRIGGER orders_validate_total
BEFORE UPDATE OF total ON orders
WHEN NEW.total < 0
BEGIN
    SELECT RAISE(ABORT, 'Order total cannot be negative');
END;
```

## Instead Of Trigger

```sql
CREATE TRIGGER active_users_update
INSTEAD OF UPDATE OF name ON active_users
BEGIN
    UPDATE users
    SET name = NEW.name
    WHERE id = OLD.id;
END;
```

## Old and New Values

```text
NEW.column  New row value for INSERT and UPDATE
OLD.column  Previous row value for UPDATE and DELETE
```

## Inspect and Drop

```sql
SELECT name, tbl_name, sql
FROM sqlite_schema
WHERE type = 'trigger';

DROP TRIGGER IF EXISTS users_after_insert;
```
