# Nginx : Reverse Proxy

## Basic Proxy

```nginx
server {
    listen 80;
    server_name app.example.com;

    location / {
        proxy_pass http://127.0.0.1:3000;
        proxy_http_version 1.1;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

## Timeouts

```nginx
location /api/ {
    proxy_pass http://127.0.0.1:3000;
    proxy_connect_timeout 5s;
    proxy_send_timeout 30s;
    proxy_read_timeout 30s;
}
```

## WebSocket

```nginx
map $http_upgrade $connection_upgrade {
    default upgrade;
    ''      close;
}

location /socket/ {
    proxy_pass http://127.0.0.1:3000;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection $connection_upgrade;
}
```

## Validate Backend

```bash
curl -I http://127.0.0.1:3000
curl -I https://app.example.com
sudo nginx -t
```
