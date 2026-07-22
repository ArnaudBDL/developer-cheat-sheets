# Express : Security

## Application Hardening

```javascript
const app = express();

app.disable('x-powered-by');
app.set('trust proxy', 1);
app.use(express.json({ limit: '1mb' }));
app.use(express.urlencoded({ extended: false, limit: '1mb' }));
```

## Secure Cookies

```javascript
response.cookie('session', value, {
  httpOnly: true,
  secure: true,
  sameSite: 'lax',
  path: '/',
});
```

## Dependency Checks

```bash
npm audit
npm outdated
npm ci
```

## Security Checklist

- Validate all untrusted request data.
- Use parameterized database queries.
- Set explicit payload and upload limits.
- Apply authentication and authorization independently.
- Protect state-changing browser requests against CSRF.
- Configure CORS for only the required origins and methods.
- Set security headers and TLS at the appropriate HTTP boundary.
- Avoid returning stack traces or internal errors to clients.
- Use rate limits and timeouts for exposed endpoints.
- Keep Express, Node.js and dependencies updated.
