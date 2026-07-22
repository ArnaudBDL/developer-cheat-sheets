# Nginx : Troubleshooting

## Configuration

```bash
sudo nginx -t
sudo nginx -T
nginx -V
sudo systemctl status nginx
sudo journalctl -u nginx -n 100
```

## Listening Ports

```bash
sudo ss -lntp | grep -E ':80|:443'
sudo lsof -nP -iTCP:80 -sTCP:LISTEN
sudo lsof -nP -iTCP:443 -sTCP:LISTEN
```

## HTTP and TLS

```bash
curl -I http://127.0.0.1
curl -I -H 'Host: example.com' http://127.0.0.1
curl -Iv https://example.com
openssl s_client -connect example.com:443 -servername example.com -brief
```

## Common Errors

```text
403 Forbidden
  Check filesystem permissions, root or alias, index files and access rules.

404 Not Found
  Check server_name, location matching, root, alias and try_files.

413 Content Too Large
  Check client_max_body_size.

502 Bad Gateway
  Check upstream availability, address, protocol and socket permissions.

503 Service Unavailable
  Check rate limits, upstream availability and maintenance rules.

504 Gateway Timeout
  Check upstream latency and proxy timeouts.
```

## Backend and Logs

```bash
curl -I http://127.0.0.1:3000
sudo tail -f /var/log/nginx/error.log
sudo tail -f /var/log/nginx/access.log
```

## Permissions

```bash
namei -l /var/www/example.com/public/index.html
sudo -u www-data test -r /var/www/example.com/public/index.html
```
