# TypeScript : Type Guards

## typeof and instanceof

```typescript
function format(value: string | number): string {
  return typeof value === 'number' ? value.toFixed(2) : value.trim();
}

if (error instanceof Error) {
  console.error(error.message);
}
```

## in Operator

```typescript
type Cat = { meow(): void };
type Dog = { bark(): void };

function speak(animal: Cat | Dog): void {
  if ('meow' in animal) {
    animal.meow();
  } else {
    animal.bark();
  }
}
```

## Type Predicate

```typescript
function isUser(value: unknown): value is User {
  return typeof value === 'object'
    && value !== null
    && 'id' in value
    && 'name' in value;
}
```

## Assertion Function

```typescript
function assertUser(value: unknown): asserts value is User {
  if (!isUser(value)) {
    throw new TypeError('Invalid user');
  }
}
```

## Exhaustiveness

```typescript
function assertNever(value: never): never {
  throw new Error(`Unexpected value: ${String(value)}`);
}
```
