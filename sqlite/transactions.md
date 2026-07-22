# SQLite : Transactions

## Basic Transaction

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 100
WHERE id = 1;

UPDATE accounts
SET balance = balance + 100
WHERE id = 2;

COMMIT;
```

## Rollback

```sql
BEGIN;
DELETE FROM orders WHERE id = 42;
ROLLBACK;
```

## Transaction Modes

```sql
BEGIN DEFERRED;
BEGIN IMMEDIATE;
BEGIN EXCLUSIVE;
```

## Savepoints

```sql
SAVEPOINT update_order;
UPDATE orders SET total = 150 WHERE id = 42;
ROLLBACK TO update_order;
RELEASE update_order;
```

`BEGIN` transactions do not nest. Use `SAVEPOINT`, `ROLLBACK TO` and `RELEASE` for nested transactional scopes.

## Busy Timeout

```sql
PRAGMA busy_timeout = 5000;
```
