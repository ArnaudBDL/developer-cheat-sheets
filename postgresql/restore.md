# PostgreSQL : Restore

## Plain SQL

```bash
createdb --host=HOST --username=postgres application
psql --host=HOST --username=postgres --dbname=application --file=application.sql
```

## Custom Format

```bash
createdb --host=HOST --username=postgres application
pg_restore --host=HOST --username=postgres --dbname=application \
  --clean --if-exists --jobs=4 application.dump
```

## Validate

```bash
psql --dbname=application --command='\dt+'
psql --dbname=application --command='ANALYZE;'
```

