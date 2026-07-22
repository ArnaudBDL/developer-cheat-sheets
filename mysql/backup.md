# MySQL : Backup

## Logical Backup

```bash
mysqldump --user=backup --password   --single-transaction   --routines   --triggers   --events   application > application.sql
```

## All Databases

```bash
mysqldump --user=backup --password   --all-databases   --single-transaction   --routines --triggers --events > all-databases.sql
```

## Compressed Backup

```bash
mysqldump --user=backup --password   --single-transaction application | gzip > application.sql.gz
sha256sum application.sql.gz
```

## Operational Rules

- Protect backup credentials and files.
- Monitor command exit status and stderr.
- Store backups outside the database host.
- Test restoration regularly.
- Capture routines, triggers and events when required.
