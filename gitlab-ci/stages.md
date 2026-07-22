# GitLab CI : Stages

## Define Stage Order

```yaml
stages:
  - validate
  - build
  - test
  - deploy
```

Jobs in the same stage can run in parallel. Stages normally run sequentially in the declared order.

## Assign Jobs

```yaml
lint:
  stage: validate
  script: npm run lint

build:
  stage: build
  script: npm run build

unit-tests:
  stage: test
  script: npm test
```

## Reserved Stages

```text
.pre   Runs before user-defined stages
.post  Runs after user-defined stages
```

## Run Before Stage Order with needs

```yaml
lint:
  stage: test
  needs: []
  script: npm run lint
```

## Failure Behavior

```yaml
optional-check:
  stage: test
  script: ./optional-check.sh
  allow_failure: true
```
