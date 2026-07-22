# OAuth 2.0 : Authorization Code

## Flow

```text
Client redirects user to authorization endpoint
Authorization server authenticates user and obtains authorization
Authorization server redirects with a short-lived authorization code
Client sends the code to the token endpoint
Authorization server validates code, client and redirect URI
Authorization server issues tokens
Client calls the resource server with the access token
```

## Authorization Request

```http
GET /authorize?response_type=code&client_id=CLIENT_ID&redirect_uri=CALLBACK&scope=orders%3Aread&state=STATE HTTP/1.1
Host: authorization.example.com
```

## Token Request

```http
POST /token HTTP/1.1
Content-Type: application/x-www-form-urlencoded

grant_type=authorization_code&code=CODE&redirect_uri=CALLBACK&client_id=CLIENT_ID
```

Use PKCE, exact registered redirect URIs, single-use short-lived codes and state binding appropriate to the client protocol.
