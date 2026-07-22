# OpenID Connect : Logout

## Logout Types

```text
Local logout           Ends the Relying Party application session
RP-Initiated Logout     Relying Party asks the OpenID Provider to log out the End-User
Front-Channel Logout    Browser-based logout notification to Relying Parties
Back-Channel Logout     Direct server-to-server logout notification
```

## RP-Initiated Parameters

```text
id_token_hint
logout_hint
client_id
post_logout_redirect_uri
state
```

## Rules

- Discover and use the provider's supported logout endpoint.
- Register post-logout redirect URIs.
- Validate logout state returned to the Relying Party.
- Clear local session state even when upstream logout is unavailable, according to policy.
- Do not assume local logout automatically ends the provider session.
- Protect logout endpoints against forced or ambiguous logout behavior.
