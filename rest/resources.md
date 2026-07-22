# REST : Resources

## Resource Identification

```text
/orders
/orders/ord_123
/customers/cus_42/orders
```

## Naming

```text
Prefer nouns for resource paths.
Use stable identifiers.
Keep URI structure predictable.
Use subresources only for meaningful containment or relationships.
```

## Collection and Item

```http
GET /orders
GET /orders/ord_123
POST /orders
DELETE /orders/ord_123
```

## Rules

- Do not expose database implementation details unnecessarily.
- Avoid verbs such as `/getOrders` when HTTP methods already express the action.
- Use opaque identifiers when sequential identifiers disclose sensitive information.
- Keep resource identity distinct from a particular representation format.
- Document lifecycle, ownership and deletion semantics.
