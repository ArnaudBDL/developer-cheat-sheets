# GitLab CI : Introduction

## Core Concepts

```text
Pipeline     Complete CI/CD execution
Stage        Logical group executed in stage order
Job          Unit of work executed by a runner
Runner       Agent that executes jobs
Artifact     Job output stored and shared
Cache        Reusable files that accelerate later jobs
Environment  Deployment target such as staging or production
```

## Configuration File

```text
.gitlab-ci.yml
```

## Minimal Pipeline

```yaml
stages:
  - test

unit-tests:
  stage: test
  image: node:22-alpine
  script:
    - npm ci
    - npm test
```

## Pipeline Flow

```text
Git event
   ↓
Pipeline creation
   ↓
Rules evaluation
   ↓
Jobs assigned to runners
   ↓
Scripts executed
   ↓
Artifacts, reports and deployments
```
