# API Design : Filtering

## Simple Filters

```http
GET /orders?status=paid&customerId=cus_42
GET /users?active=true&role=editor
```

## Range Filters

```http
GET /orders?createdFrom=2026-07-01T00:00:00Z&createdTo=2026-07-31T23:59:59Z
GET /products?priceMin=10&priceMax=100
```

## Repeated Values

```http
GET /orders?status=paid&status=refunded
```

## Rules

- Allow only documented fields and operators.
- Validate values and define case sensitivity.
- Define whether repeated filters mean AND or OR.
- Apply complexity and result-size limits.
- Keep filtering syntax consistent across collections.
