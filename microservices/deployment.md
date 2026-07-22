# Microservices : Deployment

## Delivery Pipeline

```text
Source
-> Build immutable artifact
-> Unit and contract tests
-> Security and dependency checks
-> Deploy to test environment
-> Integration and smoke tests
-> Progressive production rollout
-> Verify telemetry
-> Promote or roll back
```

## Deployment Strategies

```text
Rolling
Blue-green
Canary
Feature-flagged release
```

## Rules

- Deploy services independently.
- Keep artifacts immutable between environments.
- Make database changes compatible with old and new service versions.
- Automate health verification and rollback criteria.
- Define resource requests, limits and autoscaling signals.
- Preserve version and deployment metadata in telemetry.
- Avoid coordinated releases unless the contract change truly requires them.
