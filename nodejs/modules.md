# Node.js : Modules

## ECMAScript Modules

```javascript
// math.js
export function add(left, right) {
  return left + right;
}

// app.js
import { add } from './math.js';
console.log(add(2, 3));
```

## CommonJS

```javascript
// math.cjs
function add(left, right) {
  return left + right;
}
module.exports = { add };

// app.cjs
const { add } = require('./math.cjs');
```

## Module Type

```json
{
  "type": "module"
}
```

```text
.mjs                  Explicit ECMAScript module
.cjs                  Explicit CommonJS module
.js + type=module     ECMAScript module
.js + type=commonjs   CommonJS module
```

## Built-In Modules

```javascript
import fs from 'node:fs/promises';
import path from 'node:path';
import { EventEmitter } from 'node:events';
```

## Dynamic Import

```javascript
const module = await import('./feature.js');
module.run();
```
