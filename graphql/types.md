# GraphQL : Types

```graphql
scalar DateTime

enum UserStatus {
  ACTIVE
  DISABLED
}

interface Node {
  id: ID!
}

type User implements Node {
  id: ID!
  email: String!
  status: UserStatus!
  createdAt: DateTime!
}

union SearchResult = User | Article

input CreateUserInput {
  email: String!
  name: String!
}
```

```text
Scalar       Atomic value
Object       Selectable output fields
Interface    Shared contract for object types
Union        One of several object types
Enum         Closed set of symbolic values
Input object Structured operation input
```

Use non-null markers only where the server contract can reliably guarantee a value.
