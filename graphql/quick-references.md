# GraphQL : Quick References

## Query

```graphql
query GetUser($id: ID!) {
  user(id: $id) {
    id
    name
  }
}
```

## Mutation

```graphql
mutation CreateUser($input: CreateUserInput!) {
  createUser(input: $input) {
    id
    name
  }
}
```

## Variables

```json
{
  "id": "123",
  "input": { "name": "Ada" }
}
```
