# GitHub Actions : Events

## Push and Pull Request

```yaml
on:
  push:
    branches:
      - main
      - 'release/**'
    paths:
      - 'src/**'
      - 'package.json'
  pull_request:
    branches: [main]
    types: [opened, synchronize, reopened]
```

## Schedule

```yaml
on:
  schedule:
    - cron: '0 3 * * 1'
```

## Manual Trigger

```yaml
on:
  workflow_dispatch:
```

## Workflow Call

```yaml
on:
  workflow_call:
    inputs:
      environment:
        required: true
        type: string
    secrets:
      deployment-token:
        required: true
```

## Common Events

```text
push
pull_request
workflow_dispatch
workflow_call
workflow_run
release
issues
issue_comment
schedule
repository_dispatch
```
