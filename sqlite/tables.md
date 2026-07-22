# SQLite : Tables

## Create a Table

```sql
CREATE TABLE users (
    id INTEGER PRIMARY KEY,
    email TEXT NOT NULL UNIQUE,
    name TEXT NOT NULL,
    active INTEGER NOT NULL DEFAULT 1 CHECK (active IN (0, 1)),
    created_at TEXT NOT NULL DEFAULT CURRENT_TIMESTAMP
);
```

## Foreign Keys

```sql
PRAGMA foreign_keys = ON;

CREATE TABLE orders (
    id INTEGER PRIMARY KEY,
    user_id INTEGER NOT NULL,
    total NUMERIC NOT NULL CHECK (total >= 0),
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
```

## Strict Table

```sql
CREATE TABLE settings (
    name TEXT PRIMARY KEY,
    value TEXT NOT NULL
) STRICT;
```

## Modify a Table

```sql
ALTER TABLE users RENAME TO accounts;
ALTER TABLE accounts RENAME COLUMN name TO display_name;
ALTER TABLE accounts ADD COLUMN last_login_at TEXT;
ALTER TABLE accounts DROP COLUMN last_login_at;
```

## Inspect and Delete

```sql
PRAGMA table_info(users);
PRAGMA table_xinfo(users);
PRAGMA foreign_key_list(orders);
DROP TABLE IF EXISTS temporary_data;
```
