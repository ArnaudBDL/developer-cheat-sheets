# Nginx : Quick References

## Management

```bash
nginx -t
systemctl reload nginx
systemctl restart nginx
journalctl -u nginx -f
```

## Reverse proxy

```nginx
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://127.0.0.1:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
```

## Static files

```nginx
location / {
    root /var/www/app;
    try_files $uri $uri/ /index.html;
}
```
