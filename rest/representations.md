# REST : Representations

## Example

```json
{
  "id": "ord_123",
  "status": "paid",
  "total": {
    "amount": "49.90",
    "currency": "EUR"
  }
}
```

## Representation Metadata

```http
Content-Type: application/json
Content-Language: fr
ETag: "order-17"
Last-Modified: Wed, 22 Jul 2026 08:00:00 GMT
```

## Rules

- Keep field names and types stable within a versioned contract.
- Distinguish absent, null and empty values.
- Represent money, dates and identifiers unambiguously.
- Avoid exposing internal fields by default.
- Use media types to describe representation syntax and semantics.
- Preserve links or identifiers needed to navigate related resources.
- Validate both request and response representations.
