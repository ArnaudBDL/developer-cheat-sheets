# GraphQL : Testing

```text
Schema validation
Resolver unit tests
Query integration tests
Mutation side-effect tests
Subscription delivery tests
Authorization tests by object and field
Pagination boundary tests
Error and null-propagation tests
Complexity and performance tests
Breaking-change checks
```

```typescript
const result = await execute({
  schema,
  document: parse(`
    query GetUser($id: ID!) {
      user(id: $id) { id email }
    }
  `),
  variableValues: { id: 'usr_42' },
  contextValue: authorizedContext,
})

expect(result.errors).toBeUndefined()
expect(result.data?.user).toEqual({ id: 'usr_42', email: 'user@example.com' })
```

Test the operations real clients use plus malformed inputs, unauthorized access, null values, duplicate mutations, deep queries, N+1 behavior and schema compatibility.
