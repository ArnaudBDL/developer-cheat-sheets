# Certbot : Certificates

## Obtain and Install

```bash
sudo certbot
sudo certbot run -d example.com -d www.example.com
```

## Obtain Without Installing

```bash
sudo certbot certonly -d example.com -d www.example.com
```

## Inspect Managed Certificates

```bash
sudo certbot certificates
```

## Certificate Files

```text
cert.pem       Leaf certificate
chain.pem      Issuer chain
fullchain.pem  Leaf certificate followed by issuer chain
privkey.pem    Private key
```

Reference certificate files through `/etc/letsencrypt/live/CERTIFICATE_NAME/` so services follow the current version after renewal. Protect `privkey.pem` and never copy it into source control.
