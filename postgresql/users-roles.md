# PostgreSQL : Users Roles

## Create Roles

```sql
CREATE ROLE application LOGIN PASSWORD 'strong-password';
CREATE ROLE readonly NOLOGIN;
GRANT readonly TO application;
```

## Privileges

```sql
GRANT CONNECT ON DATABASE app TO application;
GRANT USAGE ON SCHEMA public TO application;
GRANT SELECT, INSERT, UPDATE, DELETE ON ALL TABLES IN SCHEMA public TO application;
```

## Inspect

```sql
\du
SELECT rolname, rolcanlogin, rolsuper FROM pg_roles;
ALTER ROLE application PASSWORD 'new-password';
DROP ROLE application;
```

