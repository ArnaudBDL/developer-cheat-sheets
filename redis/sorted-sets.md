# Redis : Sorted Sets

## Add Members

```redis
ZADD leaderboard 100 user:1 250 user:2 175 user:3
ZADD leaderboard NX 300 user:4
ZINCRBY leaderboard 25 user:1
```

## Ranges

```redis
ZRANGE leaderboard 0 -1 WITHSCORES
ZRANGE leaderboard 0 9 REV WITHSCORES
ZRANGE leaderboard 100 200 BYSCORE WITHSCORES
ZRANGESTORE top-users leaderboard 0 9 REV
```

## Rank and Score

```redis
ZSCORE leaderboard user:2
ZRANK leaderboard user:2
ZREVRANK leaderboard user:2
ZCARD leaderboard
ZCOUNT leaderboard 100 200
```

## Remove

```redis
ZREM leaderboard user:3
ZREMRANGEBYRANK leaderboard 0 9
ZREMRANGEBYSCORE leaderboard -inf 99
```

Sorted sets store unique members ordered by numeric score.
