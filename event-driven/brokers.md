# Event-Driven Architecture : Brokers

## Broker Responsibilities

```text
Accept published messages
Persist or route messages
Deliver to subscriptions or consumers
Track acknowledgements or offsets
Apply retention and expiration
Expose operational metrics
```

## Selection Criteria

```text
Queue, pub/sub or durable stream model
Retention and replay requirements
Ordering guarantees
Delivery semantics
Throughput and latency
Partitioning and scaling
Routing capabilities
Schema integration
Security controls
Operational maturity
```

## Operational Checklist

- Define capacity, retention and message-size limits.
- Use replication and durability appropriate to the workload.
- Monitor unavailable partitions, queue depth and consumer lag.
- Test broker failover and recovery.
- Restrict administrative and data-plane access separately.

