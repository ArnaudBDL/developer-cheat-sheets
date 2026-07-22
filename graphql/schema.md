# GraphQL : Schema

```graphql
schema {
  query: Query
  mutation: Mutation
  subscription: Subscription
}

type Query {
  user(id: ID!): User
  users(first: Int = 20, after: String): UserConnection!
}

type Mutation {
  createUser(input: CreateUserInput!): CreateUserPayload!
}

type Subscription {
  userCreated: User!
}
```

The schema is the contract describing available types, fields and root operations. Validate documents against it and review schema changes for compatibility.
