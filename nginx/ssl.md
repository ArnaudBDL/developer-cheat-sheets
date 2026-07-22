# Nginx : SSL

## HTTPS Server

```nginx
server {
    listen 443 ssl;
    listen [::]:443 ssl;
    server_name example.com;

    ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;

    root /var/www/example.com/public;
}
```

## HTTP Redirect

```nginx
server {
    listen 80;
    listen [::]:80;
    server_name example.com www.example.com;
    return 301 https://example.com$request_uri;
}
```

## Validate

```bash
sudo nginx -t
sudo systemctl reload nginx
curl -Iv https://example.com
openssl s_client -connect example.com:443 -servername example.com -brief
```

## HSTS

```nginx
add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;
```

Enable HSTS only after confirming reliable HTTPS coverage for every intended hostname.
