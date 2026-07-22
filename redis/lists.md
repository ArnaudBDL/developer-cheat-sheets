# Redis : Lists

## Push and Pop

```redis
LPUSH queue:jobs job:1
RPUSH queue:jobs job:2 job:3
LPOP queue:jobs
RPOP queue:jobs
LMPOP 1 queue:jobs LEFT COUNT 10
```

## Blocking Operations

```redis
BLPOP queue:jobs 30
BRPOP queue:jobs 30
BLMOVE queue:pending queue:processing RIGHT LEFT 30
```

## Read and Modify

```redis
LRANGE queue:jobs 0 -1
LLEN queue:jobs
LINDEX queue:jobs 0
LSET queue:jobs 0 job:updated
LTRIM queue:jobs 0 99
LREM queue:jobs 1 job:obsolete
```

Lists are ordered by insertion and support operations at both ends.
