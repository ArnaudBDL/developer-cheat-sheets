# GitHub Actions : Artifacts

## Upload an Artifact

```yaml
- uses: actions/upload-artifact@v4
  with:
    name: application-build
    path: |
      dist/
      reports/
    if-no-files-found: error
    retention-days: 7
```

## Download an Artifact

```yaml
- uses: actions/download-artifact@v4
  with:
    name: application-build
    path: downloaded-build
```

## Transfer Between Jobs

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: npm run build
      - uses: actions/upload-artifact@v4
        with:
          name: dist
          path: dist/

  deploy:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - uses: actions/download-artifact@v4
        with:
          name: dist
          path: dist/
```

## GitHub CLI

```bash
gh run download RUN_ID
gh run download RUN_ID -n application-build
gh run view RUN_ID
```
