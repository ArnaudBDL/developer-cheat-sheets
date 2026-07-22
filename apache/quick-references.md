# Apache : Quick References

## Management

```bash
apachectl configtest
apachectl -M
systemctl reload apache2
systemctl restart apache2
journalctl -u apache2 -f
```

## Virtual host

```apache
<VirtualHost *:80>
    ServerName example.com
    DocumentRoot /var/www/app/public

    <Directory /var/www/app/public>
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

## Modules and sites

```bash
a2enmod rewrite proxy proxy_http ssl
a2ensite example.conf
a2dissite example.conf
```
