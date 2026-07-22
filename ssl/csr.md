# SSL and TLS : CSR

## Generate a CSR

```bash
openssl req   -new   -key private-key.pem   -out request.csr   -subj '/C=FR/O=Example/CN=example.com'   -addext 'subjectAltName=DNS:example.com,DNS:www.example.com'
```

## Generate a Key and CSR Together

```bash
openssl req   -new   -newkey rsa:3072   -nodes   -keyout private-key.pem   -out request.csr   -subj '/C=FR/O=Example/CN=example.com'   -addext 'subjectAltName=DNS:example.com,DNS:www.example.com'
```

## Configuration File

```ini
[req]
prompt = no
distinguished_name = subject
req_extensions = extensions

[subject]
C = FR
O = Example
CN = example.com

[extensions]
subjectAltName = @alternative_names

[alternative_names]
DNS.1 = example.com
DNS.2 = www.example.com
```

```bash
openssl req -new   -key private-key.pem   -out request.csr   -config request.conf
```

## Inspect and Verify a CSR

```bash
openssl req -in request.csr -noout -text
openssl req -in request.csr -noout -subject
openssl req -in request.csr -noout -verify
```

## CSR Checklist

- Include every required hostname in Subject Alternative Names.
- Verify the subject and SANs before submission.
- Keep the private key separate from the CSR.
- Do not reuse a compromised private key.
