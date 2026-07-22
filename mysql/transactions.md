# MySQL : Transactions

## Basic Transaction

```sql
START TRANSACTION;

UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

COMMIT;
```

## Rollback and Savepoint

```sql
START TRANSACTION;
SAVEPOINT before_update;
UPDATE orders SET total = 150 WHERE id = 42;
ROLLBACK TO SAVEPOINT before_update;
RELEASE SAVEPOINT before_update;
COMMIT;
```

## Isolation

```sql
SELECT @@transaction_isolation;
SET SESSION TRANSACTION ISOLATION LEVEL READ COMMITTED;
SET TRANSACTION READ ONLY;
```

Use a transactional storage engine such as InnoDB and keep transactions short.
