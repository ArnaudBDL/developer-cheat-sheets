# Redis : Persistence

## RDB Snapshots

```conf
save 3600 1
save 300 100
save 60 10000
dbfilename dump.rdb
dir /var/lib/redis
```

```redis
BGSAVE
LASTSAVE
```

## Append-Only File

```conf
appendonly yes
appendfilename "appendonly.aof"
appendfsync everysec
auto-aof-rewrite-percentage 100
auto-aof-rewrite-min-size 64mb
```

```redis
BGREWRITEAOF
```

## Inspect Persistence

```bash
redis-cli INFO persistence
redis-cli CONFIG GET save
redis-cli CONFIG GET appendonly
redis-check-rdb /var/lib/redis/dump.rdb
redis-check-aof /var/lib/redis/appendonlydir/appendonly.aof
```

## Operational Rules

- Back up persistence files using a tested procedure.
- Monitor background save and rewrite failures.
- Verify available memory and disk space before large forks or rewrites.
- Test restoration, not only backup creation.
- Choose RDB, AOF, both or no persistence according to acceptable durability and recovery trade-offs.
