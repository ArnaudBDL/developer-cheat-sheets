# TypeScript : Types

## Primitive Types

```typescript
const name: string = 'TypeScript';
const count: number = 42;
const enabled: boolean = true;
const identifier: bigint = 42n;
const symbol: symbol = Symbol('identifier');
const missing: undefined = undefined;
const empty: null = null;
```

## Arrays and Tuples

```typescript
const values: number[] = [1, 2, 3];
const names: Array<string> = ['Alice', 'Bob'];
const coordinate: readonly [number, number] = [48.8566, 2.3522];
```

## Union and Literal Types

```typescript
type Identifier = string | number;
type Status = 'idle' | 'loading' | 'ready' | 'error';

let status: Status = 'idle';
```

## unknown, any and never

```typescript
function parse(input: unknown): string {
  if (typeof input !== 'string') {
    throw new TypeError('Expected a string');
  }

  return input;
}

function fail(message: string): never {
  throw new Error(message);
}
```

Prefer `unknown` over `any` when a value must be validated before use.
