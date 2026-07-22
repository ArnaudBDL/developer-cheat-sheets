# GitHub Actions : Secrets

## Use Secrets

```yaml
steps:
  - name: Authenticate
    env:
      API_TOKEN: ${{ secrets.API_TOKEN }}
    run: ./authenticate.sh
```

## GitHub CLI

```bash
gh secret list
gh secret set API_TOKEN
gh secret set API_TOKEN < token.txt
gh secret delete API_TOKEN
```

## Environment Secrets

```yaml
jobs:
  deploy:
    environment: production
    runs-on: ubuntu-latest
    steps:
      - env:
          DEPLOYMENT_TOKEN: ${{ secrets.DEPLOYMENT_TOKEN }}
        run: ./deploy.sh
```

## Mask a Derived Value

```bash
echo "::add-mask::$DERIVED_SECRET"
```

## Rules

- Do not print secrets or pass them through command-line arguments when avoidable.
- Do not store secrets in workflow files or artifacts.
- Use environment protection for sensitive deployments.
- Prefer short-lived credentials through OIDC when supported.
- Rotate exposed credentials immediately.
