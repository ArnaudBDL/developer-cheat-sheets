# Event-Driven Architecture : Event Sourcing

## Concept

```text
Command -> Validate -> Append domain event -> Rebuild or update state
```

Event sourcing stores the sequence of domain events as the authoritative history of an aggregate. Current state is derived by replaying those events, often with snapshots for efficiency.

## Event Store Record

```json
{
  "streamId": "order-ord_123",
  "streamVersion": 4,
  "eventId": "evt_456",
  "eventType": "order.cancelled",
  "occurredAt": "2026-07-22T10:00:00Z",
  "data": {}
}
```

## Requirements

- Append-only event storage.
- Optimistic concurrency on the stream version.
- Stable event contracts and upcasting strategy.
- Deterministic aggregate reconstruction.
- Snapshot policy when replay cost requires it.
- Tested backup, replay and migration procedures.

Event sourcing is optional and distinct from merely publishing integration events.

