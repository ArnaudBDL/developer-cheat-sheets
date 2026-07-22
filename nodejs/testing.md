# Node.js : Testing

## Built-In Test Runner

```javascript
import assert from 'node:assert/strict';
import test from 'node:test';

function add(left, right) {
  return left + right;
}

test('adds two numbers', () => {
  assert.equal(add(2, 3), 5);
});
```

## Hooks and Subtests

```javascript
import { beforeEach, describe, it } from 'node:test';

beforeEach(() => {
  // Reset state
});

describe('calculator', () => {
  it('adds values', () => {
    assert.equal(2 + 3, 5);
  });
});
```

## Mocking

```javascript
test('calls dependency', context => {
  const dependency = context.mock.fn(() => 'result');
  assert.equal(dependency(), 'result');
  assert.equal(dependency.mock.callCount(), 1);
});
```

## Run Tests

```bash
node --test
node --test test/unit/*.test.js
node --test --test-name-pattern='calculator'
node --test --experimental-test-coverage
```
