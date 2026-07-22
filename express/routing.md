# Express : Routing

## HTTP Methods

```javascript
app.get('/articles', listArticles);
app.get('/articles/:id', showArticle);
app.post('/articles', createArticle);
app.put('/articles/:id', replaceArticle);
app.patch('/articles/:id', updateArticle);
app.delete('/articles/:id', deleteArticle);
```

## Route Parameters

```javascript
app.get('/users/:userId/articles/:articleId', (request, response) => {
  response.json({
    userId: request.params.userId,
    articleId: request.params.articleId,
  });
});
```

## Multiple Handlers

```javascript
app.get('/admin', authenticate, authorize('admin'), showAdminDashboard);
```

## All Methods

```javascript
app.all('/maintenance', (request, response) => {
  response.status(503).json({ error: 'Service unavailable' });
});
```

## Chain Routes

```javascript
app.route('/articles/:id')
  .get(showArticle)
  .patch(updateArticle)
  .delete(deleteArticle);
```
