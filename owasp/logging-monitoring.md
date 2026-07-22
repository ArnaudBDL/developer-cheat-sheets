# OWASP : Logging and Monitoring

## Security Events

```text
Authentication successes and failures
Authorization denials
Administrative actions
Account and privilege changes
Validation and integrity failures
Suspicious input and rate-limit events
Security configuration changes
High-value data access
Dependency and service failures
```

## Log Content

```json
{
  "timestamp": "2026-07-22T03:00:00Z",
  "event": "authorization.denied",
  "actorId": "usr_42",
  "resource": "order",
  "resourceId": "ord_123",
  "traceId": "trace_456",
  "outcome": "denied"
}
```

## Rules

- Synchronize timestamps and use structured logs.
- Protect logs against tampering and unauthorized access.
- Avoid passwords, tokens, full payment data and unnecessary personal data.
- Correlate application, identity, infrastructure and dependency events.
- Define alerts, ownership, escalation and response procedures.
- Test that alerts reach the responsible team and contain actionable context.
