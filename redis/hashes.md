# Redis : Hashes

## Set Fields

```redis
HSET user:42 name "Arnaud" email "arnaud@example.com" active 1
HSETNX user:42 created_at "2026-07-22"
```

## Read Fields

```redis
HGET user:42 name
HMGET user:42 name email active
HGETALL user:42
HKEYS user:42
HVALS user:42
HLEN user:42
HEXISTS user:42 email
```

## Update and Delete

```redis
HINCRBY user:42 login_count 1
HINCRBYFLOAT user:42 balance 10.50
HDEL user:42 temporary_field
```

## Scan Fields

```redis
HSCAN user:42 0 MATCH preference:* COUNT 100
```

Hashes model records as field-value collections and are useful when individual fields must be read or updated independently.
