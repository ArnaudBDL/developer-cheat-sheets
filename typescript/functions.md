# TypeScript : Functions

## Typed Function

```typescript
function add(left: number, right: number): number {
  return left + right;
}
```

## Optional and Default Parameters

```typescript
function greet(name = 'Anonymous', title?: string): string {
  return title ? `Hello ${title} ${name}` : `Hello ${name}`;
}
```

## Function Type

```typescript
type Operation = (left: number, right: number) => number;

const multiply: Operation = (left, right) => left * right;
```

## Overloads

```typescript
function format(value: string): string;
function format(value: number): string;
function format(value: string | number): string {
  return String(value);
}
```

## Rest Parameters

```typescript
function total(...values: number[]): number {
  return values.reduce((sum, value) => sum + value, 0);
}
```
