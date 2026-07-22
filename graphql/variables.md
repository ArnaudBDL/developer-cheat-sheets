# GraphQL : Variables

```graphql
query UserOrders($userId: ID!, $first: Int = 20, $after: String) {
  user(id: $userId) {
    orders(first: $first, after: $after) {
      edges { cursor node { id total } }
      pageInfo { hasNextPage endCursor }
    }
  }
}
```

```json
{
  "userId": "usr_42",
  "first": 20,
  "after": null
}
```

Use variables instead of interpolating user values into operation text. Validate variable size and structure before expensive execution.
