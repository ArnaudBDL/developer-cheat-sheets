# JavaScript : Syntax

## Variables

```javascript
const applicationName = 'Application';
let counter = 0;

counter += 1;
```

Use `const` by default and `let` when reassignment is required. Avoid `var` in modern code.

## Comments

```javascript
// Single-line comment

/*
  Multi-line comment
*/
```

## Strings and Templates

```javascript
const single = 'Hello';
const double = "World";
const message = `${single}, ${double}!`;
```

## Destructuring

```javascript
const [first, second] = values;
const { id, name, active = true } = user;
```

## Spread and Rest

```javascript
const copy = [...items];
const merged = { ...defaults, ...configuration };

function total(...values) {
  return values.reduce((sum, value) => sum + value, 0);
}
```

## Optional Chaining

```javascript
const city = user.address?.city;
const result = service.execute?.();
```
