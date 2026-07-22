# JavaScript : Operators

## Arithmetic

```javascript
const sum = left + right;
const difference = left - right;
const product = left * right;
const quotient = left / right;
const remainder = left % right;
const power = left ** right;
```

## Comparison

```javascript
left === right;
left !== right;
left < right;
left <= right;
left > right;
left >= right;
```

Prefer strict equality operators `===` and `!==` when coercion is not intentional.

## Logical

```javascript
const allowed = authenticated && authorized;
const visible = publicResource || owner;
const disabled = !enabled;
```

## Nullish and Ternary

```javascript
const name = input.name ?? 'Anonymous';
const status = enabled ? 'enabled' : 'disabled';
value ??= 'default';
```

## Property Operators

```javascript
'property' in object;
object instanceof Constructor;
delete object.property;
```
