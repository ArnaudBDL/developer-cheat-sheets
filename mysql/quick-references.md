# MySQL : Quick References

## CLI

```bash
mysql -u root -p
SHOW DATABASES;
USE database_name;
SHOW TABLES;
DESCRIBE table_name;
```

## Database

```sql
CREATE DATABASE app CHARACTER SET utf8mb4;
CREATE USER 'app'@'%' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON app.* TO 'app'@'%';
```

## Backup

```bash
mysqldump -u USER -p DATABASE > backup.sql
mysql -u USER -p DATABASE < backup.sql
```
