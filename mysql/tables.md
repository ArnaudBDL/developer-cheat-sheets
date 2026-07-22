# MySQL : Tables

## Create a Table

```sql
CREATE TABLE users (
    id BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    email VARCHAR(255) NOT NULL,
    name VARCHAR(255) NOT NULL,
    active BOOLEAN NOT NULL DEFAULT TRUE,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (id),
    UNIQUE KEY uk_users_email (email)
) ENGINE=InnoDB;
```

## Foreign Key

```sql
CREATE TABLE orders (
    id BIGINT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY,
    user_id BIGINT UNSIGNED NOT NULL,
    total DECIMAL(12,2) NOT NULL,
    CONSTRAINT fk_orders_user
      FOREIGN KEY (user_id) REFERENCES users(id)
      ON DELETE CASCADE
) ENGINE=InnoDB;
```

## Inspect and Modify

```sql
SHOW TABLES;
DESCRIBE users;
SHOW CREATE TABLE users;
ALTER TABLE users ADD COLUMN last_login_at DATETIME NULL;
ALTER TABLE users DROP COLUMN last_login_at;
RENAME TABLE users TO accounts;
DROP TABLE IF EXISTS temporary_data;
```
