# Express : Routers

## Create a Router

```javascript
// src/routes/articles.js
import { Router } from 'express';
import {
  createArticle,
  deleteArticle,
  listArticles,
  showArticle,
  updateArticle,
} from '../controllers/articles.js';

export const articlesRouter = Router();

articlesRouter.get('/', listArticles);
articlesRouter.get('/:id', showArticle);
articlesRouter.post('/', createArticle);
articlesRouter.patch('/:id', updateArticle);
articlesRouter.delete('/:id', deleteArticle);
```

## Mount a Router

```javascript
import { articlesRouter } from './routes/articles.js';

app.use('/api/articles', articlesRouter);
```

## Nested Routers

```javascript
const commentsRouter = Router({ mergeParams: true });

commentsRouter.get('/', (request, response) => {
  response.json({ articleId: request.params.articleId });
});

articlesRouter.use('/:articleId/comments', commentsRouter);
```

## Router Middleware

```javascript
articlesRouter.use(authenticate);
articlesRouter.param('id', loadArticle);
```
