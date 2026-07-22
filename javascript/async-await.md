# JavaScript : Async Await

## Async Function

```javascript
async function loadUser(identifier) {
  const response = await fetch(`/api/users/${identifier}`);

  if (!response.ok) {
    throw new Error(`HTTP ${response.status}`);
  }

  return response.json();
}
```

## Error Handling

```javascript
try {
  const user = await loadUser(identifier);
  console.log(user);
} catch (error) {
  console.error(error);
} finally {
  hideLoadingIndicator();
}
```

## Parallel Operations

```javascript
const [user, orders] = await Promise.all([
  loadUser(identifier),
  loadOrders(identifier),
]);
```

## Sequential Operations

```javascript
for (const item of items) {
  await processItem(item);
}
```

## Top-Level Await

```javascript
const configuration = await loadConfiguration();
export default configuration;
```

Top-level `await` is available in JavaScript modules.
