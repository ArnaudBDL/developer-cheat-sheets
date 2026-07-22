# SQLite : Backup

## Online Backup Command

```bash
sqlite3 application.db '.backup backup.db'
```

## Vacuum Into

```bash
sqlite3 application.db "VACUUM INTO 'backup.db';"
```

## SQL Dump

```bash
sqlite3 application.db .dump > backup.sql
sqlite3 restored.db < backup.sql
```

## Backup Selected Tables

```bash
sqlite3 application.db '.dump users orders' > selected-tables.sql
```

## Verify a Backup

```bash
sqlite3 backup.db 'PRAGMA integrity_check;'
sqlite3 backup.db 'PRAGMA foreign_key_check;'
sqlite3 backup.db '.tables'
```

## Operational Rules

- Prefer SQLite backup mechanisms for a live database rather than copying only the main file during active writes.
- Store backups outside the application data directory.
- Protect backup files according to the sensitivity of the data.
- Test restoration and integrity checks regularly.
