# Apache : Security

## Reduce Information Disclosure

```apache
ServerTokens Prod
ServerSignature Off
TraceEnable Off
```

## Restrict the Filesystem

```apache
<Directory />
    AllowOverride None
    Require all denied
</Directory>

<Directory /var/www/example.com/public>
    Options -Indexes +FollowSymLinks
    AllowOverride None
    Require all granted
</Directory>

<FilesMatch "^(\.env|composer\.(json|lock)|package(-lock)?\.json)$">
    Require all denied
</FilesMatch>
```

## Protect Administration Paths

```apache
<Location /server-status>
    SetHandler server-status
    Require ip 127.0.0.1 ::1 192.168.1.0/24
</Location>
```

## Security Headers

```apache
Header always set X-Content-Type-Options "nosniff"
Header always set Referrer-Policy "strict-origin-when-cross-origin"
Header always set Content-Security-Policy "default-src 'self'"
```

## Operational Checklist

- Keep Apache, modules and the operating system updated.
- Disable unused modules and handlers.
- Run Apache with an unprivileged runtime user.
- Restrict write access to configuration and document roots.
- Avoid permissive `AllowOverride All` unless required.
- Validate configuration before reloads.
- Monitor errors, authentication failures and unexpected status codes.
- Restrict proxy destinations to prevent an open proxy.
- Use supported TLS versions and protect private keys.
