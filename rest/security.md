# REST : Security

## Core Controls

```text
TLS
Authentication
Object and function authorization
Request validation
Output encoding
Rate and size limits
Audit logging
Secret management
Dependency and platform patching
```

## Authorization

```text
Validate the caller for every request.
Authorize the requested operation.
Authorize the target object and fields.
Enforce tenant isolation.
Do not trust identifiers supplied by the client.
```

## Browser Clients

```text
Configure CORS narrowly.
Protect cookie-authenticated mutations against CSRF.
Use Secure, HttpOnly and appropriate SameSite cookie attributes.
Do not expose bearer tokens to unsafe browser storage or logs.
```

## Operational Rules

- Bound payload, query complexity and pagination size.
- Use generic public errors and detailed protected logs.
- Prevent sensitive responses from being cached incorrectly.
- Validate upstream redirects and outbound URLs.
- Test broken object-level and function-level authorization.
- Keep an inventory of endpoints, versions and owners.
