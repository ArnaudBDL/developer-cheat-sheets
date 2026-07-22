# SSL and TLS : Web Server Configuration

## Nginx

```nginx
server {
    listen 80;
    listen [::]:80;
    server_name example.com www.example.com;

    return 301 https://example.com$request_uri;
}

server {
    listen 443 ssl;
    listen [::]:443 ssl;
    server_name example.com;

    ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;

    location / {
        proxy_pass http://127.0.0.1:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-Proto https;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
```

```bash
sudo nginx -t
sudo systemctl reload nginx
```

## Apache

```apache
<VirtualHost *:80>
    ServerName example.com
    Redirect permanent / https://example.com/
</VirtualHost>

<VirtualHost *:443>
    ServerName example.com

    SSLEngine on
    SSLProtocol -all +TLSv1.2 +TLSv1.3
    SSLCertificateFile /etc/letsencrypt/live/example.com/fullchain.pem
    SSLCertificateKeyFile /etc/letsencrypt/live/example.com/privkey.pem

    ProxyPass / http://127.0.0.1:8080/
    ProxyPassReverse / http://127.0.0.1:8080/
</VirtualHost>
```

```bash
sudo apachectl configtest
sudo systemctl reload apache2
```

## Validate the Live Endpoint

```bash
curl -Iv https://example.com
openssl s_client   -connect example.com:443   -servername example.com   -verify_hostname example.com   -verify_return_error </dev/null
```

## Deployment Checklist

- Serve the full chain, not only the leaf certificate.
- Protect the private key with restricted permissions.
- Validate configuration before reloading the server.
- Confirm the certificate hostname and chain from an external client.
- Keep the HTTP listener when required for ACME HTTP-01 validation.
