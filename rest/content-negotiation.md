# REST : Content Negotiation

## Request

```http
GET /orders/ord_123 HTTP/1.1
Host: api.example.com
Accept: application/json
Accept-Language: fr
Accept-Encoding: br, gzip
```

## Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Language: fr
Content-Encoding: gzip
Vary: Accept, Accept-Language, Accept-Encoding
```

## Failure Responses

```text
406 Not Acceptable
415 Unsupported Media Type
```

## Rules

- Use `Accept` for desired response media types.
- Use `Content-Type` for the actual request or response representation.
- Emit `Vary` when caches must distinguish negotiated responses.
- Do not overload query parameters when standard negotiation headers are sufficient.
- Document supported media types and charset behavior.
