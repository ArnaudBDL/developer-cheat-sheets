# API Design : Endpoints

## Collection and Item Endpoints

```http
GET    /users
POST   /users
GET    /users/{userId}
PUT    /users/{userId}
PATCH  /users/{userId}
DELETE /users/{userId}
```

## Subresources

```http
GET  /users/{userId}/orders
POST /users/{userId}/orders
GET  /users/{userId}/orders/{orderId}
```

## Domain Actions

```http
POST /orders/{orderId}/cancellations
POST /accounts/{accountId}/password-resets
```

Model a meaningful action as a resource when it has its own validation, lifecycle, status or audit history.

## Path Rules

- Keep paths stable and readable.
- Use path parameters for resource identity.
- Use query parameters for optional selection and representation controls.
- Avoid file extensions and UI-specific routes.
