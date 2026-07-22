# GraphQL : Resolvers

```typescript
const resolvers = {
  Query: {
    user: async (_parent, args, context) => {
      await context.authorization.require('user:read', args.id)
      return context.users.findById(args.id)
    },
  },
  User: {
    orders: (user, _args, context) => context.orderLoader.load(user.id),
  },
}
```

```text
parent   Result of the parent field
args     Validated GraphQL field arguments
context  Request-scoped services and authenticated identity
info     Operation and schema execution metadata
```

Keep resolvers focused, enforce authorization at trusted boundaries, batch repeated data access and avoid hidden side effects in query fields.
