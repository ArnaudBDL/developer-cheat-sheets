# GitHub Actions : Introduction

## Core Concepts

```text
Workflow  Automated process defined in YAML
Event     Activity that triggers a workflow
Job       Group of steps executed on one runner
Step      Shell command or action invocation
Action    Reusable task
Runner    Machine that executes a job
```

## Workflow Location

```text
.github/workflows/ci.yml
```

## Minimal Workflow

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
gh run list
gh run view RUN_ID
gh run watch RUN_ID
gh run rerun RUN_ID
```
