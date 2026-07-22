# GitHub Actions : Workflows

## Workflow Structure

```yaml
name: Continuous Integration
run-name: CI for ${{ github.ref_name }}

on:
  push:
  pull_request:

permissions:
  contents: read

concurrency:
  group: ci-${{ github.ref }}
  cancel-in-progress: true

env:
  NODE_VERSION: '22'

jobs:
  test:
    runs-on: ubuntu-latest
    timeout-minutes: 15
    steps:
      - uses: actions/checkout@v4
      - run: npm test
```

## Manual Dispatch

```yaml
on:
  workflow_dispatch:
    inputs:
      environment:
        description: Deployment environment
        type: choice
        options: [staging, production]
        required: true
```

## Workflow Commands

```bash
echo "message=done" >> "$GITHUB_OUTPUT"
echo "APP_ENV=production" >> "$GITHUB_ENV"
echo "build/" >> "$GITHUB_PATH"
echo "### Build summary" >> "$GITHUB_STEP_SUMMARY"
```
