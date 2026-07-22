# Redis : Transactions

## MULTI and EXEC

```redis
MULTI
INCR account:42:operations
HSET account:42 updated_at "2026-07-22"
EXEC
```

## Discard

```redis
MULTI
SET temporary:value 1
DISCARD
```

## Optimistic Locking

```redis
WATCH inventory:item:42
GET inventory:item:42
MULTI
DECR inventory:item:42
EXEC
```

If a watched key changes before `EXEC`, the transaction is aborted. Use `UNWATCH` to cancel watches explicitly.

## Atomic Script

```redis
EVAL "local v=redis.call('GET',KEYS[1]); if v then return redis.call('INCR',KEYS[1]) end return nil" 1 counter
```

Queued transaction commands execute sequentially, but Redis transactions do not provide SQL-style rollback for command runtime errors.
