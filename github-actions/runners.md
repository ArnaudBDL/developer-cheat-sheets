# GitHub Actions : Runners

## GitHub-Hosted Runners

```yaml
runs-on: ubuntu-latest
runs-on: windows-latest
runs-on: macos-latest
```

## Self-Hosted Labels

```yaml
runs-on: [self-hosted, linux, x64, production]
```

## Runner Context

```yaml
- run: |
    echo "OS=${{ runner.os }}"
    echo "Architecture=${{ runner.arch }}"
    echo "Temporary=${{ runner.temp }}"
    echo "Tool cache=${{ runner.tool_cache }}"
```

## Service Container

```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    services:
      postgres:
        image: postgres:17-alpine
        env:
          POSTGRES_PASSWORD: postgres
        ports:
          - 5432:5432
    steps:
      - run: npm test
```

## Self-Hosted Runner Rules

- Isolate workloads according to trust level.
- Keep runner software and the operating system updated.
- Avoid persistent sensitive state between jobs.
- Restrict network access and credentials.
- Do not expose privileged self-hosted runners to untrusted pull-request code.
