# Redis : Keys

## Inspect Keys

```redis
EXISTS user:42
TYPE user:42
TTL session:token
PTTL session:token
OBJECT ENCODING user:42
```

## Expiration

```redis
EXPIRE session:token 3600
PEXPIRE session:token 1500
EXPIREAT session:token 1893456000
PERSIST session:token
```

## Rename and Delete

```redis
RENAME old:key new:key
RENAMENX old:key new:key
DEL obsolete:key
UNLINK large:key
```

## Scan Safely

```redis
SCAN 0 MATCH user:* COUNT 100
```

Use `SCAN` for incremental production iteration. Avoid `KEYS *` on large production databases because it scans the complete keyspace synchronously.

## Naming Convention

```text
application:entity:identifier
shop:user:42
shop:cart:42
shop:session:abc123
```
