# MySQL : Restore

## Restore SQL Dump

```bash
mysql --user=root --password -e 'CREATE DATABASE application;'
mysql --user=root --password application < application.sql
```

## Restore Compressed Dump

```bash
gunzip --stdout application.sql.gz |   mysql --user=root --password application
```

## Validate

```bash
mysql --user=root --password application   --execute='SHOW TABLES;'

mysqlcheck --user=root --password   --databases application
```

Restore into a separate validation environment before replacing production data when the recovery procedure permits it.
