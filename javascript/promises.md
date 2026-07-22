# JavaScript : Promises

## Create a Promise

```javascript
const promise = new Promise((resolve, reject) => {
  performOperation((error, result) => {
    if (error) {
      reject(error);
      return;
    }

    resolve(result);
  });
});
```

## Chain Promises

```javascript
loadUser(identifier)
  .then(user => loadOrders(user.id))
  .then(orders => console.log(orders))
  .catch(error => console.error(error))
  .finally(() => console.log('Complete'));
```

## Composition

```javascript
const values = await Promise.all(promises);
const results = await Promise.allSettled(promises);
const first = await Promise.race(promises);
const successful = await Promise.any(promises);
```

## Resolved and Rejected

```javascript
Promise.resolve(value);
Promise.reject(new Error('Failure'));
```

Always return a promise from a `.then()` callback when the next stage depends on its completion.
