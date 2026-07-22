# API Design : Resources

## Resource-Oriented Model

```text
/users
/users/{userId}
/users/{userId}/orders
/orders/{orderId}
```

Use nouns for resource collections and instances. Keep transport paths aligned with domain concepts.

## Relationships

```http
GET /users/42/orders
GET /orders?userId=42
```

Use a nested path when the child is naturally scoped by the parent. Use filtering when the resource is independently addressable.

## Resource Representation

```json
{
  "id": "usr_42",
  "name": "Arnaud",
  "status": "active",
  "createdAt": "2026-07-22T02:00:00Z"
}
```

## Naming Rules

- Use one casing convention for JSON properties.
- Use stable identifiers rather than mutable display values.
- Avoid implementation details in public resource names.
- Avoid mixing singular and plural collection conventions.
