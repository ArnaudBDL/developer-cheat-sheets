# JavaScript : Types

## Primitive Types

```javascript
const text = 'JavaScript';
const number = 42;
const largeInteger = 42n;
const enabled = true;
const missing = undefined;
const empty = null;
const identifier = Symbol('identifier');
```

## Objects

```javascript
const object = { name: 'JavaScript' };
const array = [1, 2, 3];
const date = new Date();
const pattern = /javascript/i;
const map = new Map();
const set = new Set();
```

## Inspect Types

```javascript
typeof value;
Array.isArray(value);
value instanceof Date;
Object.prototype.toString.call(value);
```

## Conversions

```javascript
const text = String(value);
const number = Number(value);
const integer = Number.parseInt(value, 10);
const decimal = Number.parseFloat(value);
const enabled = Boolean(value);
```

## Null and Undefined

```javascript
const fallback = value ?? 'default';
const isNull = value === null;
const isUndefined = value === undefined;
```
