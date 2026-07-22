# Event-Driven Architecture : Ordering

## Ordering Scope

```text
Global order       One total sequence across all events
Partition order    Order within a partition or shard
Entity order       Order for one aggregate or business key
No guaranteed order Consumers must tolerate arbitrary arrival order
```

## Partition Key

```text
orderId
customerId
deviceId
accountId
```

Events requiring relative order should use the same stable routing or partition key.

## Consumer Defences

- Include aggregate version or sequence number when needed.
- Ignore stale versions already applied.
- Buffer only when bounded waiting has a clear business rule.
- Define handling for gaps and missing predecessors.
- Avoid global ordering unless the business requirement justifies the scalability cost.

