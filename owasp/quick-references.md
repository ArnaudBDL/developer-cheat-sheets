# OWASP : Quick References

## Application checklist

```text
Validate input on the server
Encode output by context
Use parameterized queries
Enforce authorization on every request
Protect secrets outside source control
Set secure cookie attributes
Log security-relevant events
```

## Security headers

```http
Content-Security-Policy: default-src 'self'
X-Content-Type-Options: nosniff
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: camera=(), microphone=()
```

## Dependency checks

```bash
npm audit
composer audit
go list -m -u all
```
