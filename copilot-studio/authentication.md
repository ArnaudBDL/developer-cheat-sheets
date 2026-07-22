# Copilot Studio : Authentication

## Questions to Resolve

```text
Who may invoke the agent?
Must the user sign in?
Which identity calls each tool?
How are user and tenant boundaries enforced?
Which channels support the required authentication model?
How are tokens, secrets and sessions protected?
```

## Rules

- Configure authentication before production testing.
- Enforce authorization in tools and source systems.
- Do not rely on conversational claims about identity.
- Use approved secret and connection management.
- Test expired, revoked and insufficient credentials.
- Keep authentication differences between channels documented.
- Minimize token and identity data in logs and transcripts.
