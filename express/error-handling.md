# Express : Error Handling

## HTTP Error

```javascript
export class HttpError extends Error {
  constructor(status, message, details = undefined) {
    super(message);
    this.name = 'HttpError';
    this.status = status;
    this.details = details;
  }
}
```

## Not Found Handler

```javascript
app.use((request, response) => {
  response.status(404).json({ error: 'Route not found' });
});
```

## Error Middleware

```javascript
export function errorHandler(error, request, response, next) {
  if (response.headersSent) {
    return next(error);
  }

  const status = Number.isInteger(error.status) ? error.status : 500;
  const message = status >= 500 ? 'Internal server error' : error.message;

  if (status >= 500) {
    console.error(error);
  }

  return response.status(status).json({
    error: message,
    details: status < 500 ? error.details : undefined,
  });
}
```

## Registration Order

```javascript
app.use('/api/articles', articlesRouter);
app.use(notFoundHandler);
app.use(errorHandler);
```

Error-handling middleware uses four parameters: `error`, `request`, `response` and `next`.
