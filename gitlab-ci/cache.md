# GitLab CI : Cache

## Node.js Cache

```yaml
variables:
  NPM_CONFIG_CACHE: "$CI_PROJECT_DIR/.npm"

cache:
  key:
    files:
      - package-lock.json
  paths:
    - .npm/
```

## Per-Branch Cache

```yaml
cache:
  key: "$CI_COMMIT_REF_SLUG"
  paths:
    - vendor/
```

## Policies

```yaml
cache:
  key: dependencies
  paths:
    - .cache/
  policy: pull-push
```

```text
pull       Download existing cache only
push       Upload cache only
pull-push  Download and upload cache
```

## Cache versus Artifacts

```text
Cache      Speeds up jobs and may be absent
Artifacts  Preserve required outputs and reports
```

Do not cache secrets, credentials or required release outputs.
