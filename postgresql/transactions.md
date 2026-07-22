# PostgreSQL : Transactions

## Basic Transaction

```sql
BEGIN;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

## Savepoint

```sql
BEGIN;
SAVEPOINT before_update;
UPDATE orders SET total = 150 WHERE id = 42;
ROLLBACK TO SAVEPOINT before_update;
RELEASE SAVEPOINT before_update;
COMMIT;
```

## Isolation and Locks

```sql
BEGIN ISOLATION LEVEL SERIALIZABLE;
SELECT * FROM accounts WHERE id = 1 FOR UPDATE;
COMMIT;
```

