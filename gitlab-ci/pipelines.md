# GitLab CI : Pipelines

## Basic Pipeline

```yaml
stages:
  - build
  - test
  - deploy

build:
  stage: build
  script:
    - npm ci
    - npm run build

unit-tests:
  stage: test
  script:
    - npm test

deploy:
  stage: deploy
  script:
    - ./deploy.sh
```

## Workflow Rules

```yaml
workflow:
  rules:
    - if: $CI_PIPELINE_SOURCE == "merge_request_event"
    - if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
    - if: $CI_COMMIT_TAG
    - when: never
```

## Directed Acyclic Graph

```yaml
build:
  stage: build
  script: ./build.sh

test:
  stage: test
  needs:
    - job: build
      artifacts: true
  script: ./test.sh
```

## Pipeline Sources

```text
push
merge_request_event
schedule
web
api
trigger
pipeline
parent_pipeline
```

## Validate Configuration

Use GitLab CI Lint in the project interface to validate merged YAML configuration before running the pipeline.
