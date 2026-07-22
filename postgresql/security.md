# PostgreSQL : Security

## Client Authentication

```conf
# pg_hba.conf
hostssl application application 10.0.0.0/24 scram-sha-256
host all all 0.0.0.0/0 reject
```

## TLS and Passwords

```conf
ssl = on
password_encryption = 'scram-sha-256'
```

## Least Privilege

```sql
REVOKE CREATE ON SCHEMA public FROM PUBLIC;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT SELECT ON TABLES TO readonly;
ALTER TABLE tenant_data ENABLE ROW LEVEL SECURITY;
```

## Checklist

```text
Restrict network exposure, use SCRAM and TLS, grant minimum privileges, protect configuration and backups, rotate credentials, update PostgreSQL, and test restores.
```

