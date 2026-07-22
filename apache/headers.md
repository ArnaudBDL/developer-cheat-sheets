# Apache : Headers

## Enable mod_headers

```bash
sudo a2enmod headers
sudo systemctl reload apache2
```

## Security Headers

```apache
Header always set X-Content-Type-Options "nosniff"
Header always set Referrer-Policy "strict-origin-when-cross-origin"
Header always set Permissions-Policy "camera=(), microphone=(), geolocation=()"
Header always set Content-Security-Policy "default-src 'self'"
```

## HSTS

```apache
Header always set Strict-Transport-Security "max-age=31536000; includeSubDomains"
```

## Remove Headers

```apache
Header always unset X-Powered-By
Header always unset Server
```

The `Server` header may also be influenced by `ServerTokens` and `ServerSignature`.

## Proxy Headers

```apache
RequestHeader set X-Forwarded-Proto "https"
RequestHeader set X-Forwarded-Port "443"
ProxyPreserveHost On
```

## Inspect Headers

```bash
curl -I https://example.com
curl -v https://example.com/
```
