# SQLite : CLI

## Open a Database

```bash
sqlite3 application.db
sqlite3 -readonly application.db
sqlite3 :memory:
```

## Essential Dot Commands

```text
.help
.databases
.tables
.schema
.schema table_name
.indexes
.headers on
.mode column
.quit
```

Dot commands belong to the `sqlite3` shell and do not end with a semicolon. SQL statements do.

## Output Modes

```text
.mode column
.mode box
.mode csv
.mode json
.mode line
.mode list
.headers on
.nullvalue NULL
```

## Execute SQL

```bash
sqlite3 application.db 'SELECT * FROM users LIMIT 10;'
sqlite3 application.db < schema.sql
sqlite3 application.db '.read migration.sql'
```

## Import and Export CSV

```text
.mode csv
.import --skip 1 users.csv users
.headers on
.once users.csv
SELECT * FROM users;
```

## Shell Safety

```bash
sqlite3 --safe application.db
```
