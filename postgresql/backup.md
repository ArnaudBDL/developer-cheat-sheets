# PostgreSQL : Backup

## Plain SQL

```bash
pg_dump --host=HOST --username=backup --dbname=application \
  --format=plain --clean --if-exists --file=application.sql
```

## Custom Format

```bash
pg_dump --host=HOST --username=backup --dbname=application \
  --format=custom --file=application.dump
pg_dumpall --host=HOST --username=postgres --globals-only > globals.sql
```

## Verify

```bash
pg_restore --list application.dump
sha256sum application.dump
```

