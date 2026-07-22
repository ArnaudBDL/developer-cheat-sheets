# SSL and TLS : Security

## Protocol Configuration

```text
Enable TLS 1.2 and TLS 1.3
Disable SSL and obsolete TLS versions
Prefer forward-secret modern cipher suites
Use authenticated encryption modes
Keep TLS libraries and web servers updated
```

## Private-Key Protection

```bash
chmod 600 private-key.pem
chown root:root private-key.pem
```

- Store keys outside source control.
- Limit key access to the service that requires it.
- Use a secrets manager, HSM or managed key service when appropriate.
- Replace keys and certificates after suspected compromise.

## HTTP Security Headers

```http
Strict-Transport-Security: max-age=31536000; includeSubDomains
Content-Security-Policy: default-src 'self'
X-Content-Type-Options: nosniff
Referrer-Policy: strict-origin-when-cross-origin
```

Enable HSTS only after confirming that HTTPS is correctly deployed for the intended hosts.

## Certificate Checklist

```text
Correct Subject Alternative Names
Trusted and complete certificate chain
Valid certificate dates
Appropriate Key Usage and Extended Key Usage
Secure signature and public-key algorithms
Working automated renewal
Independent expiration monitoring
```

## Inspect the Endpoint

```bash
openssl s_client -connect example.com:443 -servername example.com -brief
openssl s_client -connect example.com:443 -servername example.com -tls1_2
openssl s_client -connect example.com:443 -servername example.com -tls1_3
curl -Iv https://example.com
```

## Avoid

- Self-signed certificates for public services unless clients explicitly trust them.
- Private keys embedded in images or repositories.
- Wildcard certificates without strict key protection.
- Manual renewal without monitoring.
- Disabling certificate verification to bypass trust failures.
