# Redis : Sets

## Add and Remove

```redis
SADD user:42:roles editor reviewer
SREM user:42:roles reviewer
SPOP temporary:members
```

## Inspect

```redis
SMEMBERS user:42:roles
SISMEMBER user:42:roles editor
SMISMEMBER user:42:roles editor admin
SCARD user:42:roles
SRANDMEMBER user:42:roles 2
SSCAN user:42:roles 0 COUNT 100
```

## Set Operations

```redis
SINTER team:a team:b
SUNION team:a team:b
SDIFF team:a team:b
SINTERSTORE team:common team:a team:b
SUNIONSTORE team:all team:a team:b
```

Sets store unique unordered members and support membership, intersection, union and difference operations.
