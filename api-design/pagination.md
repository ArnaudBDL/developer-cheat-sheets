# API Design : Pagination

## Cursor Pagination

```http
GET /orders?limit=50&cursor=CURSOR_VALUE
```

```json
{
  "items": [],
  "page": {
    "nextCursor": "NEXT_CURSOR",
    "hasMore": true
  }
}
```

## Offset Pagination

```http
GET /orders?limit=50&offset=100
```

## Page Pagination

```http
GET /orders?page=3&pageSize=50
```

## Rules

- Define default and maximum page sizes.
- Keep ordering deterministic with a unique tie-breaker.
- Treat cursors as opaque values.
- Define behavior when filters or sorting change between requests.
- Return totals only when their cost and consistency are acceptable.
