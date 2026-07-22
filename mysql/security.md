# MySQL : Security

## Secure Installation

```bash
sudo mysql_secure_installation
```

## Network Restriction

```ini
[mysqld]
bind-address = 127.0.0.1
require_secure_transport = ON
```

## Least Privilege

```sql
CREATE USER 'application'@'localhost' IDENTIFIED BY 'strong-password';
GRANT SELECT, INSERT, UPDATE, DELETE
ON application.* TO 'application'@'localhost';
SHOW GRANTS FOR 'application'@'localhost';
```

## TLS Status

```sql
SHOW VARIABLES LIKE 'require_secure_transport';
SHOW STATUS LIKE 'Ssl_cipher';
```

## Checklist

- Use least-privilege accounts and restrictive host patterns.
- Use parameterized queries in applications.
- Restrict network exposure and require encrypted connections where appropriate.
- Protect data files, logs, configuration and backups.
- Keep MySQL and the operating system updated.
- Test backup restoration and incident recovery.
