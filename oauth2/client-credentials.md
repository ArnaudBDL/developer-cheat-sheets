# OAuth 2.0 : Client Credentials

## Use Case

```text
A confidential client obtains an access token for its own identity and permissions.
No resource owner or end-user delegation is involved.
```

## Token Request

```http
POST /token HTTP/1.1
Host: authorization.example.com
Authorization: Basic BASE64_CLIENT_CREDENTIALS
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials&scope=reports%3Aread
```

## Rules

- Use only for confidential clients.
- Authenticate the client with an approved mechanism.
- Grant only machine-appropriate permissions.
- Keep credentials in a secret-management system.
- Rotate credentials and audit token issuance.
- Do not represent the token as an end-user identity.
- Prefer workload identity or asymmetric credentials where the platform supports them.
