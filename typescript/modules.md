# TypeScript : Modules

## Named Exports

```typescript
// math.ts
export const pi = Math.PI;
export function add(left: number, right: number): number {
  return left + right;
}

// application.ts
import { add, pi } from './math.js';
```

## Type-Only Imports

```typescript
import type { User } from './user.js';
export type { User } from './user.js';
```

## Default and Namespace Imports

```typescript
import Application from './application.js';
import * as math from './math.js';
```

## Dynamic Import

```typescript
const module = await import('./feature.js');
module.activate();
```

## Package Type

```json
{
  "type": "module"
}
```
