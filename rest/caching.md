# REST : Caching

## Freshness

```http
Cache-Control: public, max-age=300
Cache-Control: private, max-age=60
Cache-Control: no-store
```

## Validation

```http
ETag: "order-17"
```

```http
GET /orders/ord_123 HTTP/1.1
If-None-Match: "order-17"
```

```http
HTTP/1.1 304 Not Modified
```

## Rules

- Define cacheability deliberately for every representation.
- Use `private` for user-specific responses that browser caches may retain.
- Use `no-store` when storage is prohibited.
- Use validators to avoid retransmitting unchanged representations.
- Emit `Vary` for negotiated or authorization-sensitive dimensions.
- Do not cache data across users or tenants without a correct cache key and policy.
- Invalidate or revalidate derived caches after mutations.
