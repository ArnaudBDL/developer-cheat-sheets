# GraphQL : Directives

```graphql
query UserDetails($includeEmail: Boolean!, $skipOrders: Boolean!) {
  user(id: "usr_42") {
    id
    email @include(if: $includeEmail)
    orders @skip(if: $skipOrders) { id }
  }
}
```

```graphql
directive @auth(requires: Role!) on FIELD_DEFINITION

type Query {
  auditLog: [AuditEntry!]! @auth(requires: ADMIN)
}
```

Built-in directives alter execution for selected fields or fragments. Custom directives need documented locations, semantics, validation and authorization behavior.
