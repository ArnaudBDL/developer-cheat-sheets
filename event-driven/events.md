# Event-Driven Architecture : Events

## Event Anatomy

```json
{
  "id": "evt_01J2ABCDEF",
  "type": "order.created",
  "source": "orders-service",
  "subject": "orders/ord_123",
  "time": "2026-07-22T10:00:00Z",
  "schemaVersion": 1,
  "correlationId": "cor_456",
  "causationId": "cmd_789",
  "data": {
    "orderId": "ord_123",
    "customerId": "cus_42"
  }
}
```

## Naming

```text
order.created
order.cancelled
payment.authorized
inventory.reservation.failed
```

Use past-tense names for facts. Keep commands, requests and events distinct.

## Rules

- Give every event a globally unique identifier.
- Include event time and schema version.
- Carry correlation and causation identifiers when tracing workflows.
- Include enough data for the intended consumers without exposing unnecessary sensitive information.
- Do not mutate a published event.

