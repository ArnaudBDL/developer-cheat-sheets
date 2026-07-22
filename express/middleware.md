# Express : Middleware

## Custom Middleware

```javascript
export function requestLogger(request, response, next) {
  const startedAt = performance.now();

  response.on('finish', () => {
    const duration = Math.round(performance.now() - startedAt);
    console.log(request.method, request.originalUrl, response.statusCode, duration);
  });

  next();
}
```

## Built-In Middleware

```javascript
app.use(express.json({ limit: '1mb' }));
app.use(express.urlencoded({ extended: false }));
app.use('/assets', express.static('public', {
  immutable: true,
  maxAge: '1d',
}));
```

## Mount Middleware

```javascript
app.use(requestLogger);
app.use('/api', authenticate);
app.post('/articles', validateArticle, createArticle);
```

## Execution Rule

A middleware must either finish the response or call `next()` to transfer control to the next function.
