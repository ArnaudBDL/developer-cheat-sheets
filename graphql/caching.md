# GraphQL : Caching

```http
POST /graphql
Content-Type: application/json
```

```text
Client normalized cache   Stores entities by stable identity
Resolver cache            Reuses field or data-source results
Request batching          Combines repeated entity loads
Persisted operations      Identifies approved operations by hash
CDN or HTTP cache         Suitable only when transport and authorization semantics permit
```

- Include identity, tenant and authorization scope in cache keys.
- Define TTL and invalidation rules.
- Do not cache sensitive responses across callers.
- Avoid caching errors indefinitely.
- Use stable object identifiers and type names for normalized caches.
