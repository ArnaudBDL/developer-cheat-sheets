# Nginx : Performance

## Workers and Connections

```nginx
worker_processes auto;
worker_rlimit_nofile 65535;

events {
    worker_connections 4096;
    multi_accept on;
}
```

## HTTP Settings

```nginx
sendfile on;
tcp_nopush on;
tcp_nodelay on;
keepalive_timeout 30;
keepalive_requests 1000;
reset_timedout_connection on;
```

## Open File Cache

```nginx
open_file_cache max=10000 inactive=30s;
open_file_cache_valid 60s;
open_file_cache_min_uses 2;
open_file_cache_errors on;
```

## Upstream Keepalive

```nginx
upstream application_backend {
    server 127.0.0.1:3000;
    keepalive 32;
}

location / {
    proxy_http_version 1.1;
    proxy_set_header Connection "";
    proxy_pass http://application_backend;
}
```

## Measure

```bash
curl -o /dev/null -s -w 'connect=%{time_connect} total=%{time_total}
' https://example.com
ab -n 1000 -c 20 https://example.com/
```

Tune from measured traffic, memory, file-descriptor limits, latency and upstream capacity.
