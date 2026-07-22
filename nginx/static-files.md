# Nginx : Static Files

## Serve a Directory

```nginx
server {
    listen 80;
    server_name example.com;
    root /var/www/example.com/public;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

## Single-Page Application

```nginx
location / {
    try_files $uri $uri/ /index.html;
}
```

## Alias

```nginx
location /downloads/ {
    alias /srv/files/;
    autoindex off;
}
```

## Long-Lived Assets

```nginx
location ~* \.(?:css|js|png|jpg|jpeg|gif|svg|webp|woff2)$ {
    expires 30d;
    add_header Cache-Control "public, immutable";
    try_files $uri =404;
}
```

## Permissions

```bash
namei -l /var/www/example.com/public/index.html
sudo -u www-data test -r /var/www/example.com/public/index.html
```
