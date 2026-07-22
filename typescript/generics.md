# TypeScript : Generics

## Generic Function

```typescript
function identity<T>(value: T): T {
  return value;
}

const value = identity<string>('TypeScript');
```

## Generic Constraint

```typescript
function getIdentifier<T extends { id: string | number }>(value: T): T['id'] {
  return value.id;
}
```

## keyof Constraint

```typescript
function getProperty<T extends object, K extends keyof T>(object: T, key: K): T[K] {
  return object[key];
}
```

## Generic Interface and Class

```typescript
interface Repository<T, ID = number> {
  findById(id: ID): Promise<T | null>;
}

class MemoryRepository<T extends { id: number }> implements Repository<T> {
  constructor(private readonly values: T[]) {}

  async findById(id: number): Promise<T | null> {
    return this.values.find(value => value.id === id) ?? null;
  }
}
```
