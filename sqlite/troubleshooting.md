# SQLite : Troubleshooting

## Database Integrity

```bash
sqlite3 application.db 'PRAGMA quick_check;'
sqlite3 application.db 'PRAGMA integrity_check;'
sqlite3 application.db 'PRAGMA foreign_key_check;'
```

## Inspect Database State

```bash
sqlite3 application.db '.databases'
sqlite3 application.db '.tables'
sqlite3 application.db '.schema'
sqlite3 application.db 'PRAGMA journal_mode;'
sqlite3 application.db 'PRAGMA database_list;'
```

## Common Problems

```text
database is locked
  Check concurrent writers, long transactions, busy timeout and process ownership.

attempt to write a readonly database
  Check database and parent-directory permissions, mount mode and application user.

no such table
  Confirm the opened database path, attached databases, migrations and schema.

foreign key constraint failed
  Enable foreign keys and inspect parent rows, child rows and delete behavior.

malformed database schema or database disk image is malformed
  Stop writes, preserve the original files and work from a copy during recovery.
```

## File and Process Checks

```bash
ls -lah application.db*
stat application.db
lsof application.db
file application.db
df -h .
df -i .
```

## Recover with the CLI

```bash
sqlite3 corrupt.db '.recover' > recovered.sql
sqlite3 recovered.db < recovered.sql
sqlite3 recovered.db 'PRAGMA integrity_check;'
```

Always retain the original database and associated journal or WAL files before attempting recovery.
