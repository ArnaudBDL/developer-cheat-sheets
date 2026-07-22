# Event-Driven Architecture : CQRS

## Concept

```text
Command side
  Validate intent -> Change authoritative state -> Publish event

Query side
  Consume events -> Build read model -> Serve optimized queries
```

CQRS separates the model used to change state from the model used to answer queries. The separation may be logical or physical.

## Read Model

```json
{
  "orderId": "ord_123",
  "customerName": "Customer",
  "status": "paid",
  "total": 149.90,
  "lastUpdatedAt": "2026-07-22T10:00:00Z"
}
```

## Design Questions

```text
Is separate optimization actually required?
What staleness is acceptable?
How are projections rebuilt?
How are projection failures detected?
How is read-your-own-write handled?
Who owns each read model?
```

CQRS adds operational and consistency complexity. Use it where separate write and read models solve a concrete problem.

