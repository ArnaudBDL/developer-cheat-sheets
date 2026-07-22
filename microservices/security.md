# Microservices : Security

## Trust Boundaries

```text
External client -> gateway
Gateway -> service
Service -> service
Service -> database
Service -> broker
Deployment platform -> workload
```

## Controls

- Authenticate users, workloads and administrators.
- Authorize each operation and target object at the owning service.
- Use least-privileged workload identities.
- Encrypt external and sensitive internal transport.
- Store secrets outside images and source repositories.
- Validate all inputs at service boundaries.
- Segment networks and restrict ingress and egress.
- Protect software supply chains and verify artifacts.
- Audit privileged actions and security-policy changes.
- Apply consistent patching and vulnerability management.

## Service Checklist

```text
Identity
Authorization
Input validation
Data classification
Secrets
Network policy
Dependency security
Audit events
Rate limits
Incident ownership
```

