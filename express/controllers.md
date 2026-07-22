# Express : Controllers

## Controller Functions

```javascript
// src/controllers/articles.js
export async function listArticles(request, response) {
  const articles = await request.services.articles.findAll();
  response.status(200).json({ data: articles });
}

export async function showArticle(request, response) {
  const article = await request.services.articles.findById(request.params.id);

  if (!article) {
    return response.status(404).json({ error: 'Article not found' });
  }

  return response.status(200).json({ data: article });
}

export async function createArticle(request, response) {
  const article = await request.services.articles.create(request.body);
  return response
    .location(`/api/articles/${article.id}`)
    .status(201)
    .json({ data: article });
}
```

## Thin Controllers

Controllers should coordinate HTTP input and output while delegating business rules, persistence and integrations to dedicated services.

## Bind Services

```javascript
app.use((request, response, next) => {
  request.services = services;
  next();
});
```
