# JavaScript : Arrays

## Create and Access

```javascript
const items = ['one', 'two', 'three'];
const first = items[0];
const last = items.at(-1);
```

## Add and Remove

```javascript
items.push('four');
items.pop();
items.unshift('zero');
items.shift();
items.splice(1, 1);
```

## Transform

```javascript
const doubled = values.map(value => value * 2);
const active = users.filter(user => user.active);
const total = values.reduce((sum, value) => sum + value, 0);
const found = users.find(user => user.id === identifier);
```

## Test Values

```javascript
const hasActive = users.some(user => user.active);
const allActive = users.every(user => user.active);
const includes = items.includes('two');
```

## Copy and Sort

```javascript
const copy = [...items];
const ascending = [...values].sort((left, right) => left - right);
const reversed = [...items].reverse();
```

## Destructuring

```javascript
const [first, second, ...remaining] = items;
```
