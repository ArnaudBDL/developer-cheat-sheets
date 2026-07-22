# Express : Requests

## Request Data

```javascript
const identifier = request.params.id;
const page = request.query.page;
const payload = request.body;
const token = request.get('authorization');
const contentType = request.get('content-type');
```

## Request Information

```javascript
console.log(request.method);
console.log(request.path);
console.log(request.originalUrl);
console.log(request.protocol);
console.log(request.hostname);
console.log(request.ip);
console.log(request.ips);
console.log(request.secure);
```

## Content Negotiation

```javascript
const acceptedType = request.accepts(['json', 'html']);
const acceptedLanguage = request.acceptsLanguages('fr', 'en');
```

## Cookies

```javascript
const sessionCookie = request.get('cookie');
```

Treat path parameters, query parameters, headers, cookies and request bodies as untrusted input.
