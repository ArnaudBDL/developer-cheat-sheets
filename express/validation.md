# Express : Validation

## Validate Route Parameters

```javascript
export function validateIdentifier(request, response, next) {
  const identifier = Number.parseInt(request.params.id, 10);

  if (!Number.isSafeInteger(identifier) || identifier <= 0) {
    return response.status(400).json({ error: 'Invalid identifier' });
  }

  request.params.id = identifier;
  return next();
}
```

## Validate a Request Body

```javascript
export function validateArticle(request, response, next) {
  const { title, content } = request.body ?? {};
  const errors = [];

  if (typeof title !== 'string' || title.trim().length < 3) {
    errors.push({ field: 'title', message: 'Title is invalid' });
  }

  if (typeof content !== 'string' || content.trim() === '') {
    errors.push({ field: 'content', message: 'Content is required' });
  }

  if (errors.length > 0) {
    return response.status(422).json({ errors });
  }

  request.validatedBody = {
    title: title.trim(),
    content: content.trim(),
  };

  return next();
}
```

## Validation Rules

- Validate at trust boundaries.
- Reject unexpected types and invalid ranges.
- Normalize only after validation.
- Keep validation errors structured and predictable.
- Do not rely on client-side validation alone.
