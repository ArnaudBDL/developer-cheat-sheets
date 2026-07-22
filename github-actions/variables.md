# GitHub Actions : Variables

## Workflow Environment Variables

```yaml
env:
  NODE_ENV: test

jobs:
  test:
    runs-on: ubuntu-latest
    env:
      CI: true
    steps:
      - env:
          LOG_LEVEL: debug
        run: npm test
```

## Configuration Variables

```yaml
- run: echo "${{ vars.DEPLOYMENT_REGION }}"
```

## Default Variables

```bash
echo "$GITHUB_REPOSITORY"
echo "$GITHUB_REF"
echo "$GITHUB_SHA"
echo "$GITHUB_RUN_ID"
echo "$GITHUB_WORKSPACE"
echo "$RUNNER_OS"
```

## Create Variables During a Job

```yaml
- run: echo "VERSION=1.2.0" >> "$GITHUB_ENV"
- run: echo "$VERSION"
```

## GitHub CLI

```bash
gh variable list
gh variable set DEPLOYMENT_REGION --body europe-west1
gh variable delete DEPLOYMENT_REGION
```
