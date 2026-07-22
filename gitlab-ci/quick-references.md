# GitLab CI : Quick References

## Pipeline skeleton

```yaml
stages:
  - test
  - build

test:
  stage: test
  script:
    - npm ci
    - npm test

build:
  stage: build
  script:
    - npm run build
  artifacts:
    paths:
      - dist/
```

## Rules and cache

```yaml
default:
  cache:
    key: ${CI_COMMIT_REF_SLUG}
    paths:
      - node_modules/

job:
  rules:
    - if: $CI_COMMIT_BRANCH == "main"
```
