# JavaScript : Errors

## Throw and Catch

```javascript
try {
  const result = execute();
  console.log(result);
} catch (error) {
  console.error(error.message);
} finally {
  cleanup();
}
```

## Custom Error

```javascript
class ValidationError extends Error {
  constructor(message, details = []) {
    super(message);
    this.name = 'ValidationError';
    this.details = details;
  }
}

throw new ValidationError('Invalid input', [{ field: 'email' }]);
```

## Error Cause

```javascript
try {
  await repository.save(entity);
} catch (cause) {
  throw new Error('Unable to save entity', { cause });
}
```

## Inspect Errors

```javascript
error.name;
error.message;
error.stack;
error.cause;
```

## Aggregate Errors

```javascript
try {
  await Promise.any(promises);
} catch (error) {
  if (error instanceof AggregateError) {
    console.error(error.errors);
  }
}
```
