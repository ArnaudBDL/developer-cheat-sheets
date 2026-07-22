# OpenID Connect : Sessions

## Session Layers

```text
OpenID Provider session  Authentication state maintained by the provider
Relying Party session    Local application state created after token validation
Browser state            Cookies and transaction state used by each party
```

## Local Session Controls

```text
Secure cookie
HttpOnly cookie
Appropriate SameSite policy
Session rotation after authentication
Idle and absolute timeout
Reauthentication for sensitive operations
Server-side revocation where required
```

## Rules

- Do not use ID-token lifetime as the only local-session policy.
- Rotate local session identifiers after sign-in.
- Define whether the application honors provider-session changes.
- Keep local session termination and upstream logout behavior explicit.
- Protect state-changing requests against CSRF where cookies are used.
- Record authentication time and assurance only when validated and needed.
