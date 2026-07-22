# GraphQL : Pagination

```graphql
type PageInfo {
  hasNextPage: Boolean!
  hasPreviousPage: Boolean!
  startCursor: String
  endCursor: String
}

type UserEdge {
  cursor: String!
  node: User!
}

type UserConnection {
  edges: [UserEdge!]!
  pageInfo: PageInfo!
}
```

```graphql
query Users($first: Int!, $after: String) {
  users(first: $first, after: $after) {
    edges { cursor node { id email } }
    pageInfo { hasNextPage endCursor }
  }
}
```

Treat cursors as opaque, define page-size limits and use deterministic ordering with a unique tie-breaker.
