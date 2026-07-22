# GitLab CI : Variables

## Global and Job Variables

```yaml
variables:
  NODE_ENV: test
  NPM_CONFIG_CACHE: "$CI_PROJECT_DIR/.npm"

build:
  variables:
    NODE_ENV: production
  script:
    - npm run build
```

## Predefined Variables

```bash
echo "$CI_PROJECT_PATH"
echo "$CI_COMMIT_SHA"
echo "$CI_COMMIT_SHORT_SHA"
echo "$CI_COMMIT_BRANCH"
echo "$CI_COMMIT_TAG"
echo "$CI_PIPELINE_ID"
echo "$CI_JOB_ID"
echo "$CI_DEFAULT_BRANCH"
```

## Dotenv Variables

```yaml
prepare:
  script:
    - echo "VERSION=1.2.0" > build.env
  artifacts:
    reports:
      dotenv: build.env
```

## File-Type Variables

```yaml
deploy:
  script:
    - application --certificate "$TLS_CERTIFICATE"
```

A file-type CI/CD variable exposes a temporary file path rather than placing the full value directly in the environment variable.

## Shell Expansion

```bash
printf '%s
' "$VARIABLE_NAME"
printf '%s
' "${VARIABLE_NAME:-default}"
```
