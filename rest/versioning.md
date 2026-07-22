# REST : Versioning

## Compatibility

```text
Usually compatible
  Adding optional response fields
  Adding optional request fields
  Adding new resources

Usually breaking
  Removing or renaming fields
  Changing field types or meanings
  Making optional fields mandatory
  Changing status or error semantics
```

## Version Strategies

```text
Path version       /v1/orders
Media type version application/vnd.example.order-v1+json
Header version     Explicit version request header
```

## Lifecycle

```text
Publish contract
Announce deprecation
Provide migration guidance
Observe consumer adoption
Maintain supported overlap
Retire according to policy
```

- Version only when compatibility cannot be preserved.
- Keep resource identity separate from representation version when possible.
- Test old consumers against new server releases.
- Document support and retirement policies.
- Avoid silent behavioral changes within a published version.
