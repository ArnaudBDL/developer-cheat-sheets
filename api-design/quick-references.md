# API Design : Quick References

## Resource conventions

```text
GET    /resources
POST   /resources
GET    /resources/{id}
PATCH  /resources/{id}
DELETE /resources/{id}
```

## Status codes

```text
200 OK
201 Created
204 No Content
400 Bad Request
401 Unauthorized
403 Forbidden
404 Not Found
409 Conflict
422 Unprocessable Content
500 Internal Server Error
```

## Pagination

```http
GET /resources?page=2&limit=25&sort=-createdAt

{
  "data": [],
  "meta": { "page": 2, "limit": 25, "total": 0 }
}
```
