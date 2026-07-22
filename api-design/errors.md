# API Design : Errors

## Problem Details

```http
HTTP/1.1 422 Unprocessable Content
Content-Type: application/problem+json
```

```json
{
  "type": "https://api.example.com/problems/validation-error",
  "title": "Request validation failed",
  "status": 422,
  "detail": "One or more fields are invalid.",
  "instance": "/requests/req_123",
  "errors": [
    {
      "field": "email",
      "code": "invalid_format",
      "message": "A valid email address is required."
    }
  ],
  "traceId": "trace_123"
}
```

## Rules

- Keep machine-readable error codes stable.
- Keep human-readable messages safe for disclosure.
- Include a correlation identifier for support and logs.
- Do not expose stack traces, SQL, tokens or internal paths.
- Document retryable and non-retryable errors.
