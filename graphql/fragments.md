# GraphQL : Fragments

```graphql
fragment UserSummary on User {
  id
  email
  status
}

query TeamMembers($teamId: ID!) {
  team(id: $teamId) {
    members {
      ...UserSummary
    }
  }
}
```

```graphql
fragment SearchResultFields on SearchResult {
  __typename
  ... on User { id email }
  ... on Article { id title }
}
```

Use fragments for stable reusable selections. Keep them cohesive, avoid excessive nesting and include `__typename` when handling abstract types.
