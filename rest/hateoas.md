# REST : HATEOAS

## Meaning

```text
Hypermedia as the Engine of Application State lets the server advertise
available resource transitions through links and controls in representations.
```

## Example

```json
{
  "id": "ord_123",
  "status": "pending",
  "_links": {
    "self": { "href": "/orders/ord_123" },
    "cancel": { "href": "/orders/ord_123/cancellation" },
    "customer": { "href": "/customers/cus_42" }
  }
}
```

## Common Relations

```text
self
next
prev
first
last
collection
related
```

## Rules

- Advertise only transitions available in the current state.
- Use documented and stable relation names.
- Keep clients dependent on relation semantics rather than URI construction.
- Document custom relation vocabularies.
- Choose and apply a consistent hypermedia format.
- Test link presence, absence and authorization behavior.
