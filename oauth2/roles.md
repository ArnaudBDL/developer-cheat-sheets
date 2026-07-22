# OAuth 2.0 : Roles

## Core Roles

```text
Resource Owner        Entity capable of granting access to a protected resource
Client                Application requesting protected-resource access
Authorization Server  Issues tokens after authenticating and authorizing the grant
Resource Server       Hosts protected resources and validates access tokens
```

## Client Types

```text
Confidential client  Can protect credentials in its execution environment
Public client        Cannot reliably keep a client secret confidential
```

## Trust Rules

- Register clients and redirect URIs explicitly.
- Do not treat a public client secret as confidential authentication.
- Keep authorization decisions at the authorization server and resource server.
- Do not expose resource-owner credentials to clients.
- Separate user-delegated grants from machine-to-machine grants.
