# MySQL : Users and Privileges

## Create Accounts

```sql
CREATE USER 'application'@'localhost' IDENTIFIED BY 'strong-password';
CREATE USER 'reporting'@'10.0.0.%' IDENTIFIED BY 'strong-password';
```

## Grant Privileges

```sql
GRANT SELECT, INSERT, UPDATE, DELETE
ON application.*
TO 'application'@'localhost';

GRANT SELECT
ON application.*
TO 'reporting'@'10.0.0.%';
```

## Inspect and Revoke

```sql
SHOW GRANTS FOR 'application'@'localhost';
SELECT user, host, account_locked FROM mysql.user;
REVOKE DELETE ON application.* FROM 'application'@'localhost';
```

## Manage Accounts

```sql
ALTER USER 'application'@'localhost' IDENTIFIED BY 'new-password';
ALTER USER 'application'@'localhost' ACCOUNT LOCK;
ALTER USER 'application'@'localhost' ACCOUNT UNLOCK;
DROP USER 'application'@'localhost';
```
