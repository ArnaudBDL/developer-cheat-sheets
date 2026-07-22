# Apache : Virtual Hosts

## HTTP Virtual Host

```apache
<VirtualHost *:80>
    ServerName example.com
    ServerAlias www.example.com
    DocumentRoot /var/www/example.com/public

    <Directory /var/www/example.com/public>
        Options -Indexes +FollowSymLinks
        AllowOverride None
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/example-error.log
    CustomLog ${APACHE_LOG_DIR}/example-access.log combined
</VirtualHost>
```

## Enable and Disable

```bash
sudo a2ensite example.conf
sudo a2dissite 000-default.conf
sudo apachectl configtest
sudo systemctl reload apache2
```

## Red Hat Family

Place virtual-host files in `/etc/httpd/conf.d/` and reload `httpd` after validation.

```bash
sudo apachectl configtest
sudo systemctl reload httpd
```

## Inspect Virtual Hosts

```bash
apachectl -S
apachectl -t -D DUMP_VHOSTS
curl -I -H 'Host: example.com' http://127.0.0.1
```

## Redirect www to Apex

```apache
<VirtualHost *:80>
    ServerName www.example.com
    Redirect permanent / https://example.com/
</VirtualHost>
```
