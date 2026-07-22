# Express : Responses

## Send Responses

```javascript
response.send('Hello');
response.json({ status: 'ok' });
response.status(201).json(resource);
response.sendStatus(204);
response.end();
```

## Headers

```javascript
response.set('Cache-Control', 'no-store');
response.type('application/json');
response.location('/articles/42');
response.vary('Accept-Encoding');
```

## Redirect and Download

```javascript
response.redirect(303, '/articles');
response.download('/srv/files/report.pdf', 'report.pdf');
response.sendFile('/srv/public/index.html');
```

## Cookies

```javascript
response.cookie('session', token, {
  httpOnly: true,
  secure: true,
  sameSite: 'lax',
  maxAge: 3600000,
});

response.clearCookie('session');
```

## Check Completion

```javascript
if (!response.headersSent) {
  response.status(500).json({ error: 'Internal server error' });
}
```
