# Apache : SSL

## Enable TLS

```bash
sudo a2enmod ssl headers
sudo systemctl reload apache2
```

## HTTPS Virtual Host

```apache
<VirtualHost *:443>
    ServerName example.com
    DocumentRoot /var/www/example.com/public

    SSLEngine on
    SSLProtocol -all +TLSv1.2 +TLSv1.3
    SSLCertificateFile /etc/letsencrypt/live/example.com/fullchain.pem
    SSLCertificateKeyFile /etc/letsencrypt/live/example.com/privkey.pem

    Header always set Strict-Transport-Security "max-age=31536000; includeSubDomains"

    <Directory /var/www/example.com/public>
        Options -Indexes +FollowSymLinks
        AllowOverride None
        Require all granted
    </Directory>
</VirtualHost>
```

## HTTP Redirect

```apache
<VirtualHost *:80>
    ServerName example.com
    ServerAlias www.example.com
    Redirect permanent / https://example.com/
</VirtualHost>
```

## Validate Configuration

```bash
sudo apachectl configtest
sudo systemctl reload apache2
curl -Iv https://example.com
openssl s_client -connect example.com:443 -servername example.com -brief
```

Enable HSTS only after confirming that HTTPS works reliably for all intended hostnames.
