# Apache : Troubleshooting

## Configuration Diagnostics

```bash
apachectl configtest
apachectl -S
apachectl -M
apachectl -V
apachectl -t -D DUMP_RUN_CFG
```

## Service Status

```bash
sudo systemctl status apache2
sudo journalctl -u apache2 -n 100
sudo systemctl status httpd
sudo journalctl -u httpd -n 100
```

## Listening Ports

```bash
sudo ss -lntp | grep -E ':80|:443'
sudo lsof -nP -iTCP:80 -sTCP:LISTEN
sudo lsof -nP -iTCP:443 -sTCP:LISTEN
```

## HTTP Checks

```bash
curl -I http://127.0.0.1
curl -I -H 'Host: example.com' http://127.0.0.1
curl -Iv https://example.com
```

## Common Errors

```text
403 Forbidden
  Check Require directives, directory permissions, SELinux and missing index files.

404 Not Found
  Check the selected virtual host, DocumentRoot, Alias and rewrite rules.

500 Internal Server Error
  Check the error log, invalid .htaccess directives and application handlers.

502 Bad Gateway
  Check the reverse-proxy backend, target address, protocol and timeout.

503 Service Unavailable
  Check backend capacity, maintenance rules and worker exhaustion.

AH00558 ServerName warning
  Configure a global ServerName.
```

## Permissions

```bash
namei -l /var/www/example.com/public/index.html
ls -ld /var /var/www /var/www/example.com /var/www/example.com/public
sudo -u www-data test -r /var/www/example.com/public/index.html
```

## Reverse Proxy

```bash
curl -I http://127.0.0.1:3000/
apachectl -M | grep proxy
sudo tail -f /var/log/apache2/example-error.log
```

## TLS

```bash
openssl s_client -connect example.com:443 -servername example.com -brief
openssl x509 -in certificate.pem -noout -subject -issuer -dates
```
