# GitHub Actions : Quick References

## Workflow skeleton

```yaml
name: CI
on:
  push:
    branches: [main]
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm ci
      - run: npm test
```

## GitHub CLI

```bash
gh workflow list
gh workflow run WORKFLOW
gh run list
gh run view RUN_ID --log
gh run rerun RUN_ID
```
