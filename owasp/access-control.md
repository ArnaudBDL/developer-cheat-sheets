# OWASP : Access Control

## Objectives

```text
Deny access by default.
Enforce authorization on every request.
Validate permissions on the server.
Protect object, function, field and tenant boundaries.
Use least privilege.
```

## Controls

- Centralize authorization policy and enforcement.
- Derive identity and permissions from trusted server-side context.
- Validate ownership for every object identifier.
- Restrict administrative functions by explicit role or permission.
- Prevent directory traversal and unauthorized file access.
- Apply CORS only to explicitly trusted origins and methods.
- Invalidate sessions and authorization caches after privilege changes.
- Log denied access without exposing sensitive authorization details.

## Review Checklist

```text
Anonymous versus authenticated access
Horizontal access between users
Vertical access between roles
Cross-tenant access
Field-level authorization
Bulk and export endpoints
Alternate HTTP methods
Hidden or legacy endpoints
Direct file and object references
SSRF-capable outbound requests
```
