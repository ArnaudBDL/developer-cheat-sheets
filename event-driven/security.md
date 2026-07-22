# Event-Driven Architecture : Security

## Threats

```text
Unauthorized publishing or consumption
Event tampering
Sensitive data leakage
Replay attacks
Poison messages
Schema abuse
Excessive retention
Compromised broker credentials
Cross-tenant data exposure
```

## Controls

- Authenticate producers, consumers and administrators.
- Authorize by topic, queue, operation and tenant boundary.
- Encrypt transport and stored broker data where required.
- Minimize sensitive fields and classify event data.
- Store credentials in an approved secret-management system.
- Validate event source, schema, size and content.
- Protect replay and administrative operations with elevated controls.
- Audit publishing, subscription, policy and configuration changes.
- Apply retention and deletion requirements to live, retry and dead-letter storage.

## Security Checklist

```text
Identity and credential rotation
Least-privilege ACLs
Network isolation
Encryption
Tenant isolation
Schema validation
Payload limits
Audit logging
Dead-letter protection
Replay authorization
Retention and deletion
Incident response
```

