# Redis : Quick References

## CLI

```bash
redis-cli
PING
INFO
DBSIZE
SCAN 0 MATCH "prefix:*" COUNT 100
```

## Keys

```bash
SET key value EX 3600
GET key
DEL key
EXISTS key
TTL key
EXPIRE key 3600
```

## Data structures

```bash
HSET user:1 name Ada active 1
HGETALL user:1
LPUSH queue item
RPOP queue
SADD tags docker devops
SMEMBERS tags
```
