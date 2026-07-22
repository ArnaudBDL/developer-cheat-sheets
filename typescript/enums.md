# TypeScript : Enums

## String Enum

```typescript
enum Status {
  Idle = 'idle',
  Loading = 'loading',
  Ready = 'ready',
  Error = 'error',
}
```

## Numeric Enum

```typescript
enum Direction {
  Up,
  Right,
  Down,
  Left,
}
```

## Literal Object Alternative

```typescript
const Status = {
  Idle: 'idle',
  Loading: 'loading',
  Ready: 'ready',
  Error: 'error',
} as const;

type Status = typeof Status[keyof typeof Status];
```

Literal unions or `as const` objects are often convenient when runtime enum behavior is unnecessary.
