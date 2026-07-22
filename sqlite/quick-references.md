# SQLite : Quick References

## CLI

```bash
sqlite3 app.db
.tables
.schema table_name
.headers on
.mode column
.quit
```

## Database

```sql
PRAGMA foreign_keys = ON;
CREATE TABLE users (
  id INTEGER PRIMARY KEY,
  email TEXT NOT NULL UNIQUE
);
CREATE INDEX idx_users_email ON users(email);
```

## Backup

```bash
sqlite3 app.db ".backup backup.db"
sqlite3 app.db .dump > backup.sql
```
