# GitHub Actions : Jobs

## Basic Job

```yaml
jobs:
  test:
    name: Test application
    runs-on: ubuntu-latest
    timeout-minutes: 15
    permissions:
      contents: read
    steps:
      - uses: actions/checkout@v4
      - run: npm test
```

## Dependencies

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: npm run build

  deploy:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - run: ./deploy.sh
```

## Job Conditions

```yaml
if: github.ref == 'refs/heads/main' && github.event_name == 'push'
```

## Job Outputs

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    outputs:
      version: ${{ steps.version.outputs.value }}
    steps:
      - id: version
        run: echo "value=1.2.0" >> "$GITHUB_OUTPUT"

  publish:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - run: echo "${{ needs.build.outputs.version }}"
```
