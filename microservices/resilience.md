# Microservices : Resilience

## Patterns

```text
Timeout       Bound dependency wait time
Retry         Repeat transient failures with backoff and jitter
Circuit breaker Stop calls to a persistently failing dependency
Bulkhead      Isolate resource pools and failure domains
Rate limit    Protect capacity from excess demand
Fallback      Return a safe degraded result when valid
Backpressure  Slow or reject work before overload
```

## Resilience Budget

```text
Request deadline
  Gateway budget
  Service processing budget
  Downstream call budgets
  Retry allowance
```

## Rules

- Retry only idempotent or otherwise safely repeatable work.
- Avoid multiplying retries across several layers.
- Use bounded queues.
- Design graceful degradation explicitly.
- Test dependency latency, partial outages and unavailable brokers.
- Define recovery objectives and operational runbooks.
- Measure business completion, not only service uptime.
