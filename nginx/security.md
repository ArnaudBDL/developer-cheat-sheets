# Nginx : Security

## Reduce Disclosure

```nginx
server_tokens off;
```

## Restrict Sensitive Files

```nginx
location ~ /\. {
    deny all;
}

location ~* \.(?:env|ini|log|sql|bak)$ {
    deny all;
}
```

## Limit Requests

```nginx
limit_req_zone $binary_remote_addr zone=api_rate:10m rate=10r/s;
limit_conn_zone $binary_remote_addr zone=client_connections:10m;

location /api/ {
    limit_req zone=api_rate burst=20 nodelay;
    limit_conn client_connections 20;
    proxy_pass http://application_backend;
}
```

## Restrict Administration

```nginx
location /admin/ {
    allow 192.168.1.0/24;
    deny all;
}
```

## Checklist

- Keep Nginx and the operating system updated.
- Run workers as an unprivileged user.
- Protect certificate private keys and configuration files.
- Validate hostnames, proxy destinations and trusted proxy settings.
- Set payload, connection and request-rate limits.
- Expose only required ports and locations.
- Avoid serving application secrets from the document root.
