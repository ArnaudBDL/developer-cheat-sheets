# MongoDB : Security

## Create User

```javascript
use admin
db.createUser({
  user: "application",
  pwd: passwordPrompt(),
  roles: [{ role: "readWrite", db: "application" }]
})
```

## Authentication

```yaml
security:
  authorization: enabled
net:
  bindIp: 127.0.0.1
  port: 27017
```

## Connect Securely

```bash
mongosh "mongodb://HOST:27017/application" \
  --username application \
  --authenticationDatabase admin \
  --tls \
  --tlsCAFile /path/to/ca.pem \
  --password
```

## Checklist

```text
Use least-privilege roles, restrict network exposure, enable authentication before remote access, protect key files and certificates, encrypt transport, rotate credentials, and keep MongoDB and tools updated.
```

