# TypeScript : Type Aliases

## Basic Alias

```typescript
type Identifier = string | number;
type Point = readonly [number, number];
type Handler = (event: Event) => void;
```

## Object Alias

```typescript
type User = {
  readonly id: number;
  name: string;
  roles: Role[];
};
```

## Intersection

```typescript
type Entity = { readonly id: number };
type Timestamped = { readonly createdAt: Date };
type Article = Entity & Timestamped & { title: string };
```

## Discriminated Union

```typescript
type Result<T> =
  | { status: 'success'; value: T }
  | { status: 'failure'; error: Error };
```

Use interfaces for extendable object contracts and type aliases for unions, tuples, primitives, mapped types and intersections.
