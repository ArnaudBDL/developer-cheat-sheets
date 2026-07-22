# Microservices : Observability

## Telemetry

```text
Metrics  Rates, latencies, errors, saturation and business signals
Logs     Structured events with service and correlation context
Traces   Request and workflow paths across service boundaries
```

## Required Context

```text
Timestamp
Service name and version
Environment
Trace and span identifiers
Correlation identifier
Operation
Duration
Outcome and error category
```

## Operational Views

- Service-level objectives and error budgets
- Request rate, duration and error rate
- Resource saturation
- Dependency health
- Queue depth and oldest message age
- Deployment health and version distribution
- End-to-end business workflow completion

Use structured telemetry and preserve trace context across synchronous and asynchronous boundaries. Do not log secrets or unnecessary personal data.
