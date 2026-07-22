# Apache : Rewrite Rules

## Enable Rewrite

```bash
sudo a2enmod rewrite
sudo systemctl reload apache2
```

## Basic Rewrite

```apache
RewriteEngine On
RewriteRule ^old-path$ /new-path [R=301,L]
```

## Redirect HTTP to HTTPS

```apache
RewriteEngine On
RewriteCond %{HTTPS} !=on
RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
```

## Front Controller

```apache
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^ index.php [QSA,L]
```

## Canonical Host

```apache
RewriteEngine On
RewriteCond %{HTTP_HOST} !^example\.com$ [NC]
RewriteRule ^ https://example.com%{REQUEST_URI} [R=301,L]
```

## Common Flags

```text
L    Stop processing the current rewrite rules
R    External redirect, optionally with a status code
NC   Case-insensitive match
QSA  Append the original query string
END  End per-request rewrite processing
F    Return 403 Forbidden
G    Return 410 Gone
```

## Debug Rewrite Processing

```apache
LogLevel warn rewrite:trace3
```
