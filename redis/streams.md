# Redis : Streams

## Add Entries

```redis
XADD events * type order.created order_id 42
XADD events MAXLEN ~ 10000 * type order.updated order_id 42
XLEN events
```

## Read Entries

```redis
XRANGE events - + COUNT 10
XREVRANGE events + - COUNT 10
XREAD COUNT 10 BLOCK 5000 STREAMS events $
```

## Consumer Group

```redis
XGROUP CREATE events workers $ MKSTREAM
XREADGROUP GROUP workers consumer-1 COUNT 10 BLOCK 5000 STREAMS events >
XACK events workers ENTRY_ID
XPENDING events workers
XAUTOCLAIM events workers consumer-2 60000 0-0 COUNT 10
```

## Trim and Delete

```redis
XTRIM events MAXLEN ~ 10000
XDEL events ENTRY_ID
```

Streams store append-only entries with identifiers and support consumer groups with explicit acknowledgement.
