# OAuth 2.0 : Scopes

## Scope Request

```text
scope=orders:read orders:write
```

## Scope Design

```text
resource:operation
orders:read
orders:write
profile:read
```

## Rules

- Define scopes around stable capabilities rather than UI controls.
- Request the minimum scopes needed.
- Allow the authorization server to grant a narrower scope.
- Return the granted scope when it differs from the request.
- Enforce scopes at the resource server together with object-level authorization.
- Do not use scopes as a substitute for tenant, ownership or role checks.
