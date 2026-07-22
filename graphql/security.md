# GraphQL : Security

```text
Authenticate requests and subscription connections.
Authorize every object, field and operation.
Validate variables and custom scalars.
Limit operation depth, complexity, aliases and batch size.
Enforce pagination and payload limits.
Protect introspection according to the deployment policy.
Use persisted operations where appropriate.
Apply timeouts and resource budgets.
Audit sensitive queries and mutations.
```

```text
Key risks
  Broken object-level authorization
  Excessive data exposure
  Expensive nested queries
  Alias or batching abuse
  Injection in downstream resolvers
  Subscription authorization leaks
  Introspection and schema reconnaissance
```

Never rely on a field being absent from the client query as an authorization control.
