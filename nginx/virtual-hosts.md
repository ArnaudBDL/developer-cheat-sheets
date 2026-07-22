# Nginx : Virtual Hosts

## HTTP Server Block

```nginx
server {
    listen 80;
    listen [::]:80;

    server_name example.com www.example.com;
    root /var/www/example.com/public;
    index index.html;

    access_log /var/log/nginx/example-access.log;
    error_log /var/log/nginx/example-error.log;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

## Enable a Site

```bash
sudo ln -s /etc/nginx/sites-available/example.conf   /etc/nginx/sites-enabled/example.conf
sudo nginx -t
sudo systemctl reload nginx
```

## Default Catch-All

```nginx
server {
    listen 80 default_server;
    listen [::]:80 default_server;
    server_name _;
    return 444;
}
```

## Redirect www

```nginx
server {
    listen 80;
    server_name www.example.com;
    return 301 https://example.com$request_uri;
}
```
