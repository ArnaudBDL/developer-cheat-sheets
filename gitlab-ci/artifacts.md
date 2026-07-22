# GitLab CI : Artifacts

## Store Build Output

```yaml
build:
  script:
    - npm run build
  artifacts:
    name: "build-$CI_COMMIT_SHORT_SHA"
    paths:
      - dist/
    expire_in: 7 days
    when: on_success
```

## Transfer to Another Job

```yaml
test:
  needs:
    - job: build
      artifacts: true
  script:
    - test -d dist
```

## Test Reports

```yaml
unit-tests:
  script:
    - npm test -- --reporter=junit
  artifacts:
    when: always
    reports:
      junit: reports/junit.xml
    paths:
      - reports/
```

## Coverage Report

```yaml
artifacts:
  reports:
    coverage_report:
      coverage_format: cobertura
      path: coverage/cobertura-coverage.xml
```

## Exclude Files

```yaml
artifacts:
  paths:
    - build/
  exclude:
    - build/**/*.map
```
