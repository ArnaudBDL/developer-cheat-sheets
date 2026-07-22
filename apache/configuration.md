# Apache : Configuration

## Main Configuration

```apache
ServerRoot "/etc/apache2"
Listen 80
ServerName server.example.com
DocumentRoot "/var/www/html"

<Directory "/var/www/html">
    Options -Indexes +FollowSymLinks
    AllowOverride None
    Require all granted
</Directory>
```

## Configuration Test

```bash
apachectl configtest
apachectl -t
apachectl -S
apachectl -M
apachectl -V
```

## Reload Safely

```bash
sudo apachectl configtest && sudo systemctl reload apache2
sudo apachectl configtest && sudo systemctl reload httpd
```

## Include Files

```apache
IncludeOptional conf-enabled/*.conf
IncludeOptional sites-enabled/*.conf
IncludeOptional conf.d/*.conf
```

## Environment Variables

```apache
SetEnv APP_ENV production
PassEnv EXTERNAL_VARIABLE
```

## Inspect Parsed Configuration

```bash
apachectl -t -D DUMP_VHOSTS
apachectl -t -D DUMP_RUN_CFG
apachectl -t -D DUMP_MODULES
```
