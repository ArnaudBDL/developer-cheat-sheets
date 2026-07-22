# SSL and TLS : Troubleshooting

## Inspect the Live Server

```bash
openssl s_client   -connect example.com:443   -servername example.com   -showcerts   -verify_return_error </dev/null
```

## Inspect the Leaf Certificate

```bash
openssl s_client   -connect example.com:443   -servername example.com </dev/null 2>/dev/null |   openssl x509 -noout -subject -issuer -dates -ext subjectAltName
```

## Verify Hostname and Chain

```bash
openssl s_client   -connect example.com:443   -servername example.com   -verify_hostname example.com   -verify_return_error </dev/null

openssl verify   -CAfile root-ca.pem   -untrusted intermediate-ca.pem   certificate.pem
```

## Check Certificate and Key Match

```bash
openssl pkey -in private-key.pem -pubout -outform DER | openssl sha256
openssl x509 -in certificate.pem -pubkey -noout |   openssl pkey -pubin -outform DER | openssl sha256
```

## Check the Web Server

```bash
sudo nginx -t
sudo apachectl configtest
sudo ss -lntp | grep ':443'
sudo journalctl -u nginx -n 100
sudo journalctl -u apache2 -n 100
```

## Common Errors

```text
Certificate has expired
  Renew and deploy the new certificate.

Hostname mismatch
  Issue a certificate containing the hostname in Subject Alternative Names.

Unable to get local issuer certificate
  Verify that the server presents required intermediate certificates.

Self-signed certificate in certificate chain
  Install the correct chain or explicitly trust the private root where appropriate.

Key values mismatch
  Configure the private key that corresponds to the certificate public key.

Connection refused
  Confirm the server is listening on the target address and port.

Handshake failure
  Check protocol versions, cipher compatibility, SNI and server logs.
```

## Certbot Diagnostics

```bash
sudo certbot certificates
sudo certbot renew --dry-run
sudo journalctl -u certbot.service
sudo systemctl status certbot.timer
```

## Network Checks

```bash
dig +short example.com
nc -vz example.com 443
curl -Iv https://example.com
```
