# JWT : Storage

## Browser Applications

```text
Preferred pattern
  Keep sensitive session or refresh credentials in Secure, HttpOnly cookies.
  Apply an appropriate SameSite policy.
  Protect state-changing requests against CSRF.

Higher-risk pattern
  JavaScript-readable persistent storage exposes tokens to successful XSS.
```

## Native and Desktop Applications

```text
Use the operating system's protected credential storage.
Do not write tokens to ordinary configuration files or logs.
```

## Server Applications

- Store credentials in an approved secret or session store.
- Encrypt sensitive persisted token material where required.
- Restrict access by service identity and environment.
- Avoid command-line arguments, URLs, telemetry and crash reports.
- Delete expired or revoked material according to retention policy.

