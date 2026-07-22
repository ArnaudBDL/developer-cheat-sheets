# TypeScript : Objects

## Object Type

```typescript
const user: {
  readonly id: number;
  name: string;
  active?: boolean;
} = {
  id: 42,
  name: 'Arnaud',
};
```

## Index Signature

```typescript
type Configuration = {
  [key: string]: string | number | boolean;
};
```

## Record

```typescript
type Role = 'admin' | 'editor' | 'viewer';
type Permissions = Record<Role, readonly string[]>;
```

## Structural Typing

```typescript
type Named = { name: string };

function display(value: Named): string {
  return value.name;
}

display({ name: 'TypeScript', version: 7 });
```
