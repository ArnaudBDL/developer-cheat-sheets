# SQLite : Databases

## Create and Open

```bash
sqlite3 application.db
sqlite3 :memory:
```

A named database file is created when the connection performs its first persistent change.

## Inspect Database Files

```sql
PRAGMA database_list;
PRAGMA page_size;
PRAGMA page_count;
PRAGMA freelist_count;
PRAGMA journal_mode;
```

## Attach and Detach

```sql
ATTACH DATABASE 'archive.db' AS archive;
SELECT * FROM archive.orders;
DETACH DATABASE archive;
```

## Database Metadata

```sql
SELECT sqlite_version();
SELECT name, type, sql
FROM sqlite_schema
ORDER BY type, name;
```

## Vacuum

```sql
VACUUM;
VACUUM INTO 'compacted-backup.db';
PRAGMA optimize;
```
