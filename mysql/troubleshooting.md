# MySQL : Troubleshooting

## Service and Connectivity

```bash
systemctl status mysql
journalctl -u mysql -n 200
mysqladmin --user=root --password ping
ss -lntp | grep 3306
nc -vz HOST 3306
```

## Server Diagnostics

```sql
SELECT VERSION();
SHOW PROCESSLIST;
SHOW GLOBAL STATUS;
SHOW ENGINE INNODB STATUS;
SHOW WARNINGS;
```

## Common Problems

```text
Access denied
  Check account name, host component, password, authentication plugin and grants.

Can't connect to server
  Check service state, bind address, port, socket, firewall and DNS.

Too many connections
  Inspect active sessions, application pooling and max_connections.

Lock wait timeout or deadlock
  Inspect InnoDB status, transaction duration, access order and indexes.

Disk full
  Check filesystem space, inodes, binary logs, temporary files and data growth.
```

## Tables and Logs

```bash
mysqlcheck --user=root --password --all-databases
tail -f /var/log/mysql/error.log
df -h
df -i
```
