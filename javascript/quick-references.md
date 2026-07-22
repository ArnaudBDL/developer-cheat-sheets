# JavaScript : Quick References

## Collections

```javascript
const doubled = values.map(value => value * 2);
const active = users.filter(user => user.active);
const found = users.find(user => user.id === id);
const total = values.reduce((sum, value) => sum + value, 0);
```

## Async

```javascript
const response = await fetch(url);
if (!response.ok) throw new Error(`HTTP ${response.status}`);
const data = await response.json();
```

## Objects

```javascript
const copy = { ...source, enabled: true };
const { id, name } = copy;
const entries = Object.entries(copy);
```
