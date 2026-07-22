# REST : Pagination

## Offset Pagination

```http
GET /orders?offset=40&limit=20
```

## Page Pagination

```http
GET /orders?page=3&page_size=20
```

## Cursor Pagination

```http
GET /orders?limit=20&cursor=eyJpZCI6Im9yZF8xMjMifQ
```

## Response

```json
{
  "items": [],
  "page": {
    "next_cursor": "CURSOR",
    "has_more": true
  }
}
```

## Rules

- Use a stable deterministic sort.
- Treat cursors as opaque client values.
- Bound page size.
- Preserve active filters and sorting in navigation links.
- Document consistency behavior when records are inserted or deleted.
- Avoid expensive exact totals unless the product genuinely needs them.
