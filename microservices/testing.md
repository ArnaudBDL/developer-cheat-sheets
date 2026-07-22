# Microservices : Testing

## Test Layers

```text
Unit tests
Service component tests
Consumer-side contract tests
Consumer-driven contract tests
Integration tests
End-to-end workflow tests
Resilience and failure tests
Performance tests
Security tests
Deployment smoke tests
```

## Contract Test

```text
Provider contract version
Request schema
Response schema
Status and error semantics
Authentication requirements
Backward compatibility
Consumer expectations
```

## Rules

- Keep most tests below the full-system end-to-end layer.
- Test both synchronous APIs and asynchronous message contracts.
- Verify authorization across service and tenant boundaries.
- Test duplicate, delayed, missing and reordered messages.
- Inject dependency timeouts and partial failures.
- Validate rolling-version compatibility.
- Test production-like configuration and observability.
- Retest corrected incidents and known failure modes.
