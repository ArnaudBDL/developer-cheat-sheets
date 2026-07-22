# Event-Driven Architecture : Observability

## Signals

```text
Publish success and failure
Queue depth
Consumer lag
Oldest unprocessed event age
Processing latency
Retry rate
Dead-letter rate
Schema validation failures
Duplicate detection rate
Projection freshness
```

## Trace Context

```json
{
  "eventId": "evt_123",
  "correlationId": "cor_456",
  "causationId": "cmd_789",
  "traceparent": "00-TRACE_ID-SPAN_ID-01"
}
```

## Operational Dashboard

```text
Broker health
Producer error and outbox backlog
Consumer lag by group
Processing success and latency
Retry queues
Dead-letter queues
End-to-end business completion
```

Alert on user or business impact, not only infrastructure health. Preserve correlation across asynchronous boundaries.

