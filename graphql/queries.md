# GraphQL : Queries

```graphql
query GetUser($id: ID!) {
  user(id: $id) {
    id
    email
    status
  }
}
```

```json
{
  "id": "usr_42"
}
```

```graphql
query SearchUsers {
  users(first: 20) {
    edges {
      cursor
      node { id email }
    }
    pageInfo { hasNextPage endCursor }
  }
}
```

Name operations, request only required fields and enforce server-side complexity limits.
