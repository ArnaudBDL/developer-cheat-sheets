# TypeScript : Interfaces

## Declare an Interface

```typescript
interface User {
  readonly id: number;
  name: string;
  active?: boolean;
}
```

## Extend Interfaces

```typescript
interface Entity {
  readonly id: number;
}

interface Timestamped {
  readonly createdAt: Date;
}

interface Article extends Entity, Timestamped {
  title: string;
}
```

## Methods and Call Signatures

```typescript
interface Repository<T> {
  findById(id: number): Promise<T | null>;
  save(entity: T): Promise<T>;
}

interface Formatter {
  (value: unknown): string;
}
```

## Declaration Merging

```typescript
interface Settings {
  theme: string;
}

interface Settings {
  language: string;
}
```
