# Event-Driven Architecture : Dead Letter Queues

## Purpose

A dead-letter queue or dead-letter topic isolates messages that cannot be processed after the configured delivery or retry policy.

## Dead-Letter Envelope

```json
{
  "originalEvent": {},
  "failedConsumer": "billing-projection",
  "failedAt": "2026-07-22T10:15:00Z",
  "attempts": 5,
  "errorCode": "invalid_customer_reference",
  "traceId": "trace_456"
}
```

## Operational Workflow

```text
Detect
Classify
Correct code, configuration or data
Validate the correction
Replay safely
Confirm successful processing
Record the resolution
```

## Rules

- Alert on growth, age and repeated failure signatures.
- Protect dead-letter content with the same controls as the original stream.
- Never replay blindly into an unrepaired consumer.
- Preserve event identity during replay.
- Define retention and ownership.

