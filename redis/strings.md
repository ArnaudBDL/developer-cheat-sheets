# Redis : Strings

## Set and Get

```redis
SET greeting "Hello"
GET greeting
SET session:token value EX 3600
SET lock:resource token NX PX 30000
GETDEL temporary:key
```

## Multiple Values

```redis
MSET user:1:name Alice user:2:name Bob
MGET user:1:name user:2:name
MSETNX key:1 value1 key:2 value2
```

## Counters

```redis
INCR page:views
INCRBY inventory:item:42 10
DECR inventory:item:42
DECRBY inventory:item:42 5
INCRBYFLOAT account:balance 19.95
```

## String Operations

```redis
APPEND greeting " World"
STRLEN greeting
GETRANGE greeting 0 4
SETRANGE greeting 6 "Redis"
```

Redis strings are byte sequences and can store text, serialized values, counters or binary data.
