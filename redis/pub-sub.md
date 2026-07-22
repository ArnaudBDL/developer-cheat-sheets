# Redis : Pub Sub

## Subscribe and Publish

```redis
SUBSCRIBE notifications
PUBLISH notifications "Application started"
UNSUBSCRIBE notifications
```

## Pattern Subscription

```redis
PSUBSCRIBE events:*
PUBLISH events:orders "Order created"
PUNSUBSCRIBE events:*
```

## Sharded Pub/Sub

```redis
SSUBSCRIBE notifications:region:eu
SPUBLISH notifications:region:eu "Ready"
SUNSUBSCRIBE notifications:region:eu
```

## Inspect Channels

```redis
PUBSUB CHANNELS
PUBSUB NUMSUB notifications
PUBSUB NUMPAT
```

Pub/Sub messages are transient. Subscribers that are disconnected when a message is published do not receive it. Use Streams when durable processing and acknowledgement are required.
