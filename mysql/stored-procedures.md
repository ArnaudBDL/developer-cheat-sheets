# MySQL : Stored Procedures

## Create a Procedure

```sql
DELIMITER //

CREATE PROCEDURE GetUser(IN user_id BIGINT UNSIGNED)
BEGIN
    SELECT id, email, name
    FROM users
    WHERE id = user_id;
END//

DELIMITER ;
```

## Call and Inspect

```sql
CALL GetUser(42);
SHOW PROCEDURE STATUS WHERE Db = 'application';
SHOW CREATE PROCEDURE application.GetUser;
```

## Output Parameter

```sql
DELIMITER //
CREATE PROCEDURE CountActiveUsers(OUT total BIGINT)
BEGIN
    SELECT COUNT(*) INTO total FROM users WHERE active = TRUE;
END//
DELIMITER ;

CALL CountActiveUsers(@total);
SELECT @total;
```

## Drop

```sql
DROP PROCEDURE IF EXISTS GetUser;
```
