# JavaScript : Functions

## Function Declaration

```javascript
function add(left, right) {
  return left + right;
}
```

## Function Expression

```javascript
const multiply = function (left, right) {
  return left * right;
};
```

## Arrow Function

```javascript
const square = value => value ** 2;
const createUser = (id, name) => ({ id, name });
```

## Parameters

```javascript
function greet(name = 'Anonymous') {
  return `Hello ${name}`;
}

function total(...values) {
  return values.reduce((sum, value) => sum + value, 0);
}
```

## Closure

```javascript
function createCounter() {
  let count = 0;

  return () => {
    count += 1;
    return count;
  };
}
```

## Higher-Order Function

```javascript
function execute(operation, value) {
  return operation(value);
}
```
