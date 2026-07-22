# Nginx : Logs

## Access and Error Logs

```nginx
access_log /var/log/nginx/access.log;
error_log /var/log/nginx/error.log warn;
```

## Custom Format

```nginx
log_format upstream_timing '$remote_addr - $host [$time_local] '
    '"$request" $status $body_bytes_sent '
    'request_time=$request_time '
    'upstream=$upstream_addr '
    'upstream_time=$upstream_response_time';

access_log /var/log/nginx/application-access.log upstream_timing;
```

## Read Logs

```bash
sudo tail -f /var/log/nginx/access.log
sudo tail -f /var/log/nginx/error.log
sudo journalctl -u nginx -f
```

## Filter

```bash
grep ' 500 ' /var/log/nginx/access.log
grep -E ' 502 | 503 | 504 ' /var/log/nginx/access.log
grep -i 'error\|crit\|alert\|emerg' /var/log/nginx/error.log
```

## Reopen Logs

```bash
sudo nginx -s reopen
sudo logrotate -d /etc/logrotate.d/nginx
```
