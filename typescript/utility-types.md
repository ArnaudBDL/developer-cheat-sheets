# TypeScript : Utility Types

## Object Transformations

```typescript
type PartialUser = Partial<User>;
type RequiredUser = Required<User>;
type ReadonlyUser = Readonly<User>;
type UserSummary = Pick<User, 'id' | 'name'>;
type UserWithoutSecret = Omit<User, 'secret'>;
```

## Keys and Values

```typescript
type RolePermissions = Record<Role, string[]>;
type ValidStatus = Exclude<Status, 'error'>;
type TerminalStatus = Extract<Status, 'ready' | 'error'>;
type PresentName = NonNullable<string | null | undefined>;
```

## Functions

```typescript
type CreateParameters = Parameters<typeof createUser>;
type CreatedUser = ReturnType<typeof createUser>;
type AsyncUser = Awaited<ReturnType<typeof loadUser>>;
type ConstructorArguments = ConstructorParameters<typeof User>;
type UserInstance = InstanceType<typeof User>;
```

## Strings

```typescript
type Upper = Uppercase<'typescript'>;
type Lower = Lowercase<'TYPESCRIPT'>;
type Capitalized = Capitalize<'typescript'>;
type Uncapitalized = Uncapitalize<'TypeScript'>;
```
