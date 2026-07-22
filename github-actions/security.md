# GitHub Actions : Security

## Minimal Permissions

```yaml
permissions:
  contents: read

jobs:
  release:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    steps:
      - run: ./release.sh
```

## Pin Actions

```yaml
- uses: owner/action@FULL_COMMIT_SHA
```

## OIDC

```yaml
permissions:
  contents: read
  id-token: write
```

Use OIDC with a supported cloud provider to obtain short-lived credentials instead of storing long-lived cloud keys.

## Untrusted Input

Do not interpolate untrusted event data directly into shell scripts.

```yaml
- env:
    PR_TITLE: ${{ github.event.pull_request.title }}
  run: printf '%s
' "$PR_TITLE"
```

## Security Checklist

- Use least-privilege `GITHUB_TOKEN` permissions.
- Pin third-party actions and reusable workflows to trusted revisions.
- Review actions before use.
- Protect production environments with approval and branch rules.
- Do not expose secrets to untrusted fork workflows.
- Keep self-hosted runners isolated and ephemeral where possible.
- Avoid uploading secrets in logs, caches or artifacts.
- Enable dependency update and code-scanning controls where applicable.
