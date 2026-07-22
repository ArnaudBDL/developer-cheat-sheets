# MySQL : Configuration

## Common Option File

```ini
[mysqld]
bind-address = 127.0.0.1
port = 3306
datadir = /var/lib/mysql
socket = /run/mysqld/mysqld.sock
character-set-server = utf8mb4
collation-server = utf8mb4_0900_ai_ci
sql-mode = STRICT_TRANS_TABLES,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION
slow-query-log = ON
long-query-time = 1
```

## Inspect Variables

```sql
SHOW VARIABLES;
SHOW VARIABLES LIKE 'datadir';
SHOW VARIABLES LIKE 'sql_mode';
SHOW GLOBAL STATUS;
SELECT @@version, @@hostname, @@port;
```

## Configuration Files

```bash
mysqld --verbose --help | grep -A 1 'Default options'
my_print_defaults mysqld
sudo systemctl restart mysql
sudo journalctl -u mysql -n 100
```
