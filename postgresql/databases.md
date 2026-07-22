# PostgreSQL : Databases

## Create and Connect

```sql
CREATE DATABASE application OWNER application ENCODING 'UTF8';
\c application
SELECT current_database();
```

## Inspect

```sql
\l+
SELECT datname, pg_size_pretty(pg_database_size(datname)) FROM pg_database;
```

## Drop

```sql
DROP DATABASE application WITH (FORCE);
```

