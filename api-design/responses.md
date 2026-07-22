# API Design : Responses

## Resource Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
ETag: "user-42-v3"

{
  "id": "usr_42",
  "email": "user@example.com",
  "name": "User",
  "createdAt": "2026-07-22T02:00:00Z"
}
```

## Created Resource

```http
HTTP/1.1 201 Created
Location: /users/usr_42
Content-Type: application/json
```

## Collection Response

```json
{
  "items": [
    { "id": "usr_42", "name": "User" }
  ],
  "page": {
    "nextCursor": "CURSOR_VALUE",
    "hasMore": true
  }
}
```

## Rules

- Keep field types stable across responses.
- Use one date and time representation.
- Define whether absent values are omitted or returned as `null`.
- Avoid leaking internal implementation fields or secrets.
