# GitLab CI : Runners

## Runner Role

A runner executes jobs from `.gitlab-ci.yml`, using an executor such as Shell, Docker or Kubernetes.

## Runner Tags

```yaml
build-image:
  tags:
    - docker
    - linux
  script:
    - docker build -t application .
```

## Docker Image and Services

```yaml
integration-tests:
  image: node:22-alpine
  services:
    - name: postgres:17-alpine
      alias: database
  variables:
    POSTGRES_DB: application
    POSTGRES_USER: application
    POSTGRES_PASSWORD: test-password
  script:
    - npm test
```

## Runner Commands

```bash
gitlab-runner --version
gitlab-runner list
gitlab-runner verify
gitlab-runner status
gitlab-runner restart
```

## Security Rules

- Separate trusted and untrusted workloads.
- Keep GitLab Runner and executor hosts updated.
- Avoid privileged containers unless strictly required.
- Use protected runners for protected branches and tags.
- Remove persistent credentials and workspace data between jobs.
- Restrict network access from runners.
