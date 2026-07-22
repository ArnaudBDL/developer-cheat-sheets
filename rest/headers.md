# REST : Headers

## Representation Headers

```http
Content-Type: application/json
Content-Length: 512
Content-Language: en
Content-Encoding: gzip
```

## Negotiation Headers

```http
Accept: application/json
Accept-Language: fr-FR, fr;q=0.9
Accept-Encoding: br, gzip
Vary: Accept, Accept-Language
```

## Conditional Requests

```http
ETag: "order-17"
If-None-Match: "order-17"
If-Match: "order-17"
Last-Modified: Wed, 22 Jul 2026 08:00:00 GMT
If-Modified-Since: Wed, 22 Jul 2026 08:00:00 GMT
```

## Other Common Headers

```http
Authorization: Bearer TOKEN
Location: /orders/ord_123
Retry-After: 60
Link: </orders?cursor=NEXT>; rel="next"
```

Never place credentials or sensitive data in URLs or casually log authorization headers.
