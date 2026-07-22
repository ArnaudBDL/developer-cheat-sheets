# Nginx : Load Balancing

## Upstream Group

```nginx
upstream application_backend {
    server 10.0.0.11:3000;
    server 10.0.0.12:3000;
    server 10.0.0.13:3000;
}

server {
    listen 80;
    server_name app.example.com;

    location / {
        proxy_pass http://application_backend;
    }
}
```

## Algorithms

```nginx
upstream least_connections {
    least_conn;
    server 10.0.0.11:3000;
    server 10.0.0.12:3000;
}

upstream client_affinity {
    ip_hash;
    server 10.0.0.11:3000;
    server 10.0.0.12:3000;
}
```

## Weights and Failure Parameters

```nginx
upstream application_backend {
    server 10.0.0.11:3000 weight=3 max_fails=3 fail_timeout=30s;
    server 10.0.0.12:3000 weight=1 max_fails=3 fail_timeout=30s;
    server 10.0.0.13:3000 backup;
}
```

## Proxy Retry

```nginx
proxy_next_upstream error timeout http_502 http_503 http_504;
```
