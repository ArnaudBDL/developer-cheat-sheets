# Event-Driven Architecture : Quick References

## Event envelope

```json
{
  "id": "EVENT_ID",
  "type": "order.created",
  "version": 1,
  "occurredAt": "2026-01-01T00:00:00Z",
  "data": {}
}
```

## Reliability

```text
Define event schemas
Use stable event identifiers
Make consumers idempotent
Configure retries with backoff
Use dead letter queues
Track correlation and causation IDs
```

## Delivery semantics

```text
At most once
At least once
Effectively once through idempotency
```
