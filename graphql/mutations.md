# GraphQL : Mutations

```graphql
mutation CreateUser($input: CreateUserInput!) {
  createUser(input: $input) {
    user { id email status }
    errors { code field message }
  }
}
```

```json
{
  "input": {
    "email": "user@example.com",
    "name": "User"
  }
}
```

```graphql
type CreateUserPayload {
  user: User
  errors: [UserError!]!
}
```

Only top-level mutation fields should cause side effects. Use structured inputs and payloads, validate authorization, and define idempotency for retry-sensitive operations.
