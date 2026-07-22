# GitLab CI : Jobs

## Basic Job

```yaml
unit-tests:
  stage: test
  image: node:22-alpine
  before_script:
    - npm ci
  script:
    - npm test
  after_script:
    - echo "Tests completed"
  timeout: 15m
```

## Default Configuration

```yaml
default:
  image: node:22-alpine
  interruptible: true
  retry:
    max: 1
    when:
      - runner_system_failure
```

## Job Dependencies

```yaml
test:
  needs:
    - job: build
      artifacts: true
  script:
    - npm test
```

## Manual Job

```yaml
deploy-production:
  stage: deploy
  script: ./deploy.sh production
  when: manual
  allow_failure: false
```

## Hidden Job Template

```yaml
.node-job:
  image: node:22-alpine
  before_script:
    - npm ci

unit-tests:
  extends: .node-job
  script:
    - npm test
```
