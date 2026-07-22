# Nginx : Headers

## Security Headers

```nginx
add_header X-Content-Type-Options "nosniff" always;
add_header Referrer-Policy "strict-origin-when-cross-origin" always;
add_header Permissions-Policy "camera=(), microphone=(), geolocation=()" always;
add_header Content-Security-Policy "default-src 'self'" always;
```

## Proxy Request Headers

```nginx
proxy_set_header Host $host;
proxy_set_header X-Real-IP $remote_addr;
proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
proxy_set_header X-Forwarded-Proto $scheme;
```

## Hide Upstream Headers

```nginx
proxy_hide_header X-Powered-By;
```

## Inspect

```bash
curl -I https://example.com
curl -v https://example.com
```
