# GraphQL : Errors

```json
{
  "data": {
    "user": null
  },
  "errors": [
    {
      "message": "User not found",
      "path": ["user"],
      "extensions": {
        "code": "NOT_FOUND",
        "traceId": "trace_123"
      }
    }
  ]
}
```

```text
Parse error       Invalid GraphQL document syntax
Validation error  Operation is incompatible with the schema
Execution error   Resolver or downstream operation failed
Business error    Expected domain outcome represented by the contract
```

Keep machine-readable codes stable. Do not expose stack traces, database details, tokens or internal paths. Preserve correlation identifiers for support.
