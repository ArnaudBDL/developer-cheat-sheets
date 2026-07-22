# Apache : Reverse Proxy

## Enable Modules

```bash
sudo a2enmod proxy proxy_http headers
sudo systemctl reload apache2
```

## Basic Reverse Proxy

```apache
<VirtualHost *:80>
    ServerName app.example.com

    ProxyPreserveHost On
    ProxyPass / http://127.0.0.1:3000/
    ProxyPassReverse / http://127.0.0.1:3000/

    RequestHeader set X-Forwarded-Proto "http"
</VirtualHost>
```

## HTTPS Frontend

```apache
<VirtualHost *:443>
    ServerName app.example.com

    SSLEngine on
    SSLCertificateFile /etc/letsencrypt/live/app.example.com/fullchain.pem
    SSLCertificateKeyFile /etc/letsencrypt/live/app.example.com/privkey.pem

    ProxyPreserveHost On
    ProxyPass / http://127.0.0.1:3000/
    ProxyPassReverse / http://127.0.0.1:3000/

    RequestHeader set X-Forwarded-Proto "https"
</VirtualHost>
```

## Exclude a Path

```apache
ProxyPass /health !
ProxyPass / http://127.0.0.1:3000/
ProxyPassReverse / http://127.0.0.1:3000/
```

## WebSocket Proxy

```apache
ProxyPass /socket/ ws://127.0.0.1:3000/socket/
ProxyPassReverse /socket/ ws://127.0.0.1:3000/socket/
```

## Validate

```bash
apachectl configtest
curl -I http://127.0.0.1:3000/
curl -I https://app.example.com/
```
