# Apache : Logs

## Error and Access Logs

```apache
ErrorLog ${APACHE_LOG_DIR}/example-error.log
CustomLog ${APACHE_LOG_DIR}/example-access.log combined
LogLevel warn
```

## Custom Log Format

```apache
LogFormat "%v %h %l %u %t "%r" %>s %b "%{Referer}i" "%{User-Agent}i"" vhost_combined
CustomLog ${APACHE_LOG_DIR}/access.log vhost_combined
```

## Per-Module Logging

```apache
LogLevel warn rewrite:trace3 proxy:debug ssl:info
```

## Read Logs

```bash
sudo tail -f /var/log/apache2/error.log
sudo tail -f /var/log/apache2/access.log
sudo tail -f /var/log/httpd/error_log
sudo journalctl -u apache2 -f
sudo journalctl -u httpd -f
```

## Filter Logs

```bash
grep ' 500 ' access.log
grep -i 'error\|critical\|alert\|emerg' error.log
awk '$9 >= 500 {print}' access.log
```

## Log Rotation

```bash
sudo logrotate -d /etc/logrotate.conf
sudo logrotate -f /etc/logrotate.d/apache2
```
