# OWASP : Integrity

## Protected Areas

```text
Source dependencies
Build systems
CI/CD pipelines
Release artifacts
Updates
Serialized data
Configuration
Critical business records
```

## Controls

- Use trusted repositories and pinned dependency resolution.
- Review dependency provenance, ownership and maintenance.
- Protect build credentials and restrict pipeline permissions.
- Sign and verify release and update artifacts.
- Keep immutable audit evidence for sensitive changes.
- Do not deserialize untrusted objects into executable types.
- Verify integrity before loading plugins, extensions or remote configuration.
- Separate build, approval and deployment responsibilities where practical.

## Review Checklist

```text
Dependency lock files
Package provenance
Build isolation
Artifact signing
Update verification
Pipeline permissions
Secret exposure
Deserialization boundaries
Change approval
Rollback procedure
```
