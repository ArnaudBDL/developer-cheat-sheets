# Nginx : Configuration

## Common Structure

```text
/etc/nginx/
├── nginx.conf
├── conf.d/
├── mime.types
├── sites-available/
└── sites-enabled/
```

## Main Configuration

```nginx
user www-data;
worker_processes auto;
pid /run/nginx.pid;

include /etc/nginx/modules-enabled/*.conf;

events {
    worker_connections 1024;
}

http {
    include /etc/nginx/mime.types;
    default_type application/octet-stream;

    sendfile on;
    keepalive_timeout 65;

    include /etc/nginx/conf.d/*.conf;
    include /etc/nginx/sites-enabled/*;
}
```

## Validate and Reload

```bash
sudo nginx -t
sudo nginx -T
sudo nginx -t && sudo systemctl reload nginx
```

## Command-Line Control

```bash
sudo nginx -s reload
sudo nginx -s quit
sudo nginx -s stop
```
