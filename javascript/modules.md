# JavaScript : Modules

## Named Exports

```javascript
// math.js
export const pi = Math.PI;

export function add(left, right) {
  return left + right;
}
```

```javascript
import { add, pi } from './math.js';
```

## Default Export

```javascript
export default class Application {
}
```

```javascript
import Application from './application.js';
```

## Aliases and Namespace Imports

```javascript
import { add as sum } from './math.js';
import * as math from './math.js';
```

## Re-Exports

```javascript
export { add } from './math.js';
export * from './strings.js';
```

## Dynamic Import

```javascript
const module = await import('./feature.js');
module.activate();
```

## Browser Module

```html
<script type="module" src="/js/application.js"></script>
```
