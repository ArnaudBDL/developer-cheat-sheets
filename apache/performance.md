# Apache : Performance

## Inspect the MPM

```bash
apachectl -V | grep -i 'Server MPM'
apachectl -M | grep mpm
```

## Common MPMs

```text
prefork  Process-based model, commonly used where thread safety is required
worker   Hybrid multi-process and multi-threaded model
event    Worker-style model optimized for keep-alive handling
```

## Event MPM Example

```apache
<IfModule mpm_event_module>
    StartServers             2
    MinSpareThreads         25
    MaxSpareThreads         75
    ThreadLimit             64
    ThreadsPerChild         25
    MaxRequestWorkers      150
    MaxConnectionsPerChild   0
</IfModule>
```

## Compression

```apache
AddOutputFilterByType DEFLATE     text/html text/plain text/css     application/javascript application/json image/svg+xml
```

## Browser Caching

```apache
ExpiresActive On
ExpiresByType text/css "access plus 7 days"
ExpiresByType application/javascript "access plus 7 days"
ExpiresByType image/png "access plus 30 days"
ExpiresByType image/jpeg "access plus 30 days"
```

## Keep-Alive

```apache
KeepAlive On
MaxKeepAliveRequests 100
KeepAliveTimeout 2
```

## Status and Benchmarking

```bash
apachectl -M | grep status_module
curl http://127.0.0.1/server-status?auto
ab -n 1000 -c 20 https://example.com/
```

Tune worker limits from measured concurrency, memory usage, latency and backend capacity rather than copying values blindly.
