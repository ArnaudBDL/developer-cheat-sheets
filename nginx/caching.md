# Nginx : Caching

## Proxy Cache

```nginx
proxy_cache_path /var/cache/nginx 
    levels=1:2
    keys_zone=application_cache:20m
    max_size=1g
    inactive=60m
    use_temp_path=off;

server {
    location /api/ {
        proxy_pass http://application_backend;
        proxy_cache application_cache;
        proxy_cache_valid 200 10m;
        proxy_cache_valid 404 1m;
        add_header X-Cache-Status $upstream_cache_status always;
    }
}
```

## Cache Key

```nginx
proxy_cache_key "$scheme$request_method$host$request_uri";
```

## Bypass Authenticated Requests

```nginx
proxy_cache_bypass $http_authorization;
proxy_no_cache $http_authorization;
```

## Static Cache Headers

```nginx
location /assets/ {
    expires 30d;
    add_header Cache-Control "public, immutable";
}
```

Do not cache personalized or sensitive responses unless the cache key and bypass rules explicitly isolate them.
