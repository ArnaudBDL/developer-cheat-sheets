# GitLab CI : Rules

## Branch Rule

```yaml
deploy:
  script: ./deploy.sh
  rules:
    - if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
```

## Merge Request and Schedule

```yaml
job:
  script: ./job.sh
  rules:
    - if: $CI_PIPELINE_SOURCE == "merge_request_event"
      when: manual
      allow_failure: true
    - if: $CI_PIPELINE_SOURCE == "schedule"
```

## Changes

```yaml
frontend-tests:
  script: npm test
  rules:
    - changes:
        - frontend/**/*
        - package.json
        - package-lock.json
```

## Exists

```yaml
docker-build:
  script: docker build -t "$CI_REGISTRY_IMAGE:$CI_COMMIT_SHA" .
  rules:
    - exists:
        - Dockerfile
```

## Evaluation

Rules are evaluated in order until the first match. Variables created by job scripts are unavailable because rules are evaluated before jobs run.

## Avoid Duplicate Pipelines

Coordinate job `rules` with top-level `workflow: rules` so one Git event does not unintentionally create both branch and merge-request pipelines.
