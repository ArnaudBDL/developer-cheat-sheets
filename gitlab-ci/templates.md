# GitLab CI : Templates

## Hidden Job and extends

```yaml
.node-template:
  image: node:22-alpine
  before_script:
    - npm ci
  cache:
    key:
      files:
        - package-lock.json
    paths:
      - .npm/

unit-tests:
  extends: .node-template
  script:
    - npm test
```

## Local Include

```yaml
include:
  - local: .gitlab/ci/test.yml
  - local: .gitlab/ci/deploy.yml
```

## Project Include

```yaml
include:
  - project: organization/ci-templates
    ref: v1.2.0
    file: /templates/node.yml
```

## Remote Include

```yaml
include:
  - remote: https://example.com/ci/template.yml
```

## YAML Anchor

```yaml
.default-script: &default-script
  - npm ci
  - npm test

unit-tests:
  script: *default-script
```

Pin shared templates to controlled versions and review all included configuration as executable pipeline code.
