# Networking : HTTP

## Request

```http
GET /api/users/42 HTTP/1.1
Host: api.example.com
Accept: application/json
Authorization: Bearer TOKEN
```

## Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: private, max-age=60

{"id":"42","name":"User"}
```

## Methods

```text
GET      Retrieve a representation
HEAD     Retrieve metadata without a response body
POST     Submit data or create subordinate resources
PUT      Create or replace a target representation
PATCH    Apply a partial modification
DELETE   Remove a target resource
OPTIONS  Describe communication options
```

## Status Families

```text
1xx  Informational
2xx  Successful
3xx  Redirection
4xx  Client error
5xx  Server error
```

## Versions

```text
HTTP/1.1  Textual messages and persistent connections
HTTP/2    Binary framing and multiplexed streams
HTTP/3    HTTP semantics over QUIC
```

Use HTTPS for protected transport. HTTP status, TLS success and application correctness are separate diagnostic layers.
