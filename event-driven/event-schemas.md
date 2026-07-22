# Event-Driven Architecture : Event Schemas

## Schema Example

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "type": "object",
  "required": ["id", "type", "time", "data"],
  "properties": {
    "id": { "type": "string" },
    "type": { "const": "order.created" },
    "time": { "type": "string", "format": "date-time" },
    "data": {
      "type": "object",
      "required": ["orderId"],
      "properties": {
        "orderId": { "type": "string" }
      },
      "additionalProperties": false
    }
  }
}
```

## Evolution

```text
Usually compatible
  Add an optional field.
  Add an event type.
  Add an enum value only when consumers tolerate unknown values.

Usually breaking
  Remove or rename a field.
  Change a field type or meaning.
  Make an optional field mandatory.
  Reuse an event name for a different fact.
```

## Governance

- Assign an owner to every schema.
- Validate producers and consumers in CI.
- Publish compatibility rules and deprecation periods.
- Keep representative examples with the contract.
- Treat sensitive fields as part of the security review.

