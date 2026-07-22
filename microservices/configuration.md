# Microservices : Configuration

## Configuration Categories

```text
Application defaults
Environment-specific values
Feature flags
Service endpoints
Resource limits
Operational tuning
Secrets and credentials
```

## Precedence

```text
Secure runtime secret source
Environment configuration
Versioned application configuration
Safe defaults
```

## Rules

- Keep configuration external to deployable artifacts where appropriate.
- Version non-secret configuration.
- Store secrets in an approved secret-management system.
- Validate configuration at startup.
- Fail clearly on missing mandatory values.
- Audit sensitive configuration changes.
- Avoid one global configuration file shared by unrelated services.
- Define reload versus restart behavior explicitly.
