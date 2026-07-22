# OpenID Connect : Actors

## Actors

```text
End-User             Human whose identity is authenticated
Relying Party        OAuth client relying on the authentication result
OpenID Provider      Authorization server capable of authenticating the End-User
User Agent           Browser or equivalent interaction channel
```

## Responsibilities

```text
Relying Party
  Initiates authentication, validates the response and manages its local session.

OpenID Provider
  Authenticates the user, obtains authorization and issues ID tokens.

End-User
  Interacts with the provider and authorizes requested identity information.
```

- Do not authenticate users directly from unvalidated claims.
- Bind each response to the initiating Relying Party transaction.
- Keep OpenID Provider and Relying Party trust configuration explicit.
- Separate local application logout from provider-session logout.
