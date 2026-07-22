# OAuth 2.0 : Quick References

## Authorization Code with PKCE

```text
1. Generate code_verifier
2. Derive code_challenge
3. Redirect to authorization endpoint
4. Receive authorization code
5. Exchange code with code_verifier
6. Receive access token
```

## Common parameters

```text
response_type=code
client_id=CLIENT_ID
redirect_uri=CALLBACK_URL
scope=openid profile
state=RANDOM_VALUE
code_challenge=CHALLENGE
code_challenge_method=S256
```

## Token request

```http
POST /token
Content-Type: application/x-www-form-urlencoded

grant_type=authorization_code&code=CODE&redirect_uri=CALLBACK_URL&client_id=CLIENT_ID&code_verifier=VERIFIER
```
