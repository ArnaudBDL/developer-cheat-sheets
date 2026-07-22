# API Design : Requests

## Request Structure

```http
POST /users HTTP/1.1
Host: api.example.com
Content-Type: application/json
Accept: application/json
Authorization: Bearer TOKEN
Idempotency-Key: UNIQUE_KEY

{
  "email": "user@example.com",
  "name": "User"
}
```

## Validation

```text
Required fields
Data types
String formats
Numeric ranges
Collection limits
Cross-field rules
Unknown properties
Business invariants
```

## Conditional Requests

```http
If-Match: "resource-version"
If-None-Match: "resource-version"
```

## Rules

- State supported media types explicitly.
- Set size and nesting limits.
- Reject malformed or unsupported content consistently.
- Do not trust client-provided identity, authorization or computed totals.
