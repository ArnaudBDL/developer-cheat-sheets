# Microservices : Service Discovery

## Discovery Models

```text
Client-side discovery
  Client queries a registry and selects an instance.

Server-side discovery
  Client calls a stable endpoint and a proxy or load balancer selects an instance.

Platform discovery
  Orchestrator DNS or service abstraction resolves healthy instances.
```

## Required Data

```text
Service identity
Network location
Health status
Protocol and port
Version or metadata when required
```

## Rules

- Remove unhealthy or terminated instances promptly.
- Keep health checks lightweight and meaningful.
- Separate liveness from readiness.
- Avoid embedding ephemeral addresses in application configuration.
- Secure registry write and administrative access.
- Monitor stale registrations and discovery failures.
