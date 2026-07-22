# Express : Authentication

## Bearer Authentication Middleware

```javascript
export function authenticate(request, response, next) {
  const authorization = request.get('authorization');

  if (!authorization?.startsWith('Bearer ')) {
    return response.status(401).json({ error: 'Authentication required' });
  }

  const token = authorization.slice('Bearer '.length);

  try {
    request.user = request.services.tokens.verify(token);
    return next();
  } catch {
    return response.status(401).json({ error: 'Invalid credentials' });
  }
}
```

## Authorization

```javascript
export function authorize(requiredRole) {
  return (request, response, next) => {
    if (!request.user?.roles?.includes(requiredRole)) {
      return response.status(403).json({ error: 'Forbidden' });
    }

    return next();
  };
}
```

## Protect Routes

```javascript
router.get('/profile', authenticate, showProfile);
router.delete('/users/:id', authenticate, authorize('admin'), deleteUser);
```

## Cookie Settings

```javascript
response.cookie('session', sessionId, {
  httpOnly: true,
  secure: true,
  sameSite: 'lax',
});
```

Authentication verifies identity. Authorization determines whether that identity may perform an action.
