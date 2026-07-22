# API Design : Sorting

## Single Field

```http
GET /orders?sort=createdAt
GET /orders?sort=-createdAt
```

## Multiple Fields

```http
GET /orders?sort=-createdAt,id
```

## Alternative Syntax

```http
GET /orders?sortBy=createdAt&sortOrder=desc
```

## Rules

- Permit only documented sortable fields.
- Define a stable default order.
- Add a unique tie-breaker for deterministic pagination.
- Document null ordering and case sensitivity.
- Keep sorting syntax consistent across endpoints.
