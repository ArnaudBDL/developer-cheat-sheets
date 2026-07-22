# TypeScript : Quick References

## Types

```typescript
type Identifier = string | number;
interface User {
  id: Identifier;
  name: string;
  active?: boolean;
}
const users: User[] = [];
```

## Generics

```typescript
function first<T>(items: readonly T[]): T | undefined {
  return items[0];
}
type ApiResponse<T> = { data: T; error?: string };
```

## Utility types

```typescript
type UserPatch = Partial<User>;
type PublicUser = Pick<User, "id" | "name">;
type UserWithoutId = Omit<User, "id">;
type UserMap = Record<string, User>;
```
