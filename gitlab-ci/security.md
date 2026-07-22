# GitLab CI : Security

## Protected Deployment

```yaml
deploy-production:
  environment: production
  script:
    - ./deploy.sh
  rules:
    - if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
      when: manual
```

Configure production environments, branches, tags, variables and runners as protected in GitLab where appropriate.

## Sensitive Variables

```yaml
deploy:
  script:
    - application --token-file "$DEPLOYMENT_TOKEN_FILE"
```

Use masked, hidden, protected or file-type CI/CD variables according to the deployment requirements. Do not echo secret values.

## Supply-Chain Controls

- Pin container images by immutable digest for high-assurance workflows.
- Pin included templates to controlled revisions.
- Review external images and CI components.
- Separate build, test and deployment permissions.
- Use short-lived credentials or identity federation when available.
- Treat artifacts and caches as potentially sensitive.

## Runner Controls

- Do not run untrusted code on privileged or sensitive runners.
- Use protected runners for protected references.
- Isolate networks and credentials.
- Prefer ephemeral execution environments.
- Patch runner hosts and container images.

## Unsafe Logging

```bash
# Avoid
set -x
printf '%s
' "$SECRET_VALUE"
```

Do not enable shell tracing around credentials or tokens.
