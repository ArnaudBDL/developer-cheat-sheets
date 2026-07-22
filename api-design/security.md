# API Design : Security

## Security Controls

```text
Authentication
Authorization at object and operation level
TLS
Input validation
Output filtering
Rate and resource limits
Audit logging
Secret management
Dependency and patch management
Abuse detection
```

## Authorization

```text
Authenticate the caller.
Authorize the requested operation.
Authorize access to the target object.
Authorize requested fields and relationships.
Apply tenant boundaries on every data access.
```

## Headers

```http
Authorization: Bearer TOKEN
Content-Type: application/json
Accept: application/json
```

## Rules

- Deny by default and grant minimum permissions.
- Do not place credentials or sensitive data in URLs.
- Prevent mass assignment by mapping accepted fields explicitly.
- Avoid sensitive information in errors and logs.
- Define rate, payload, timeout and concurrency limits.
- Rotate credentials and revoke compromised sessions.
