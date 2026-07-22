# GitHub Actions : Steps

## Run and Uses

```yaml
steps:
  - name: Checkout repository
    uses: actions/checkout@v4

  - name: Install dependencies
    run: npm ci

  - name: Run multiline script
    shell: bash
    run: |
      npm run lint
      npm test
```

## Step Inputs

```yaml
- uses: actions/setup-node@v4
  with:
    node-version: '22'
    cache: npm
```

## Environment and Working Directory

```yaml
- name: Build frontend
  working-directory: frontend
  env:
    NODE_ENV: production
  run: npm run build
```

## Conditions and Error Control

```yaml
- run: npm test
  continue-on-error: true

- run: ./cleanup.sh
  if: always()
```

## Step Outputs

```yaml
- id: metadata
  run: echo "version=1.2.0" >> "$GITHUB_OUTPUT"

- run: echo "${{ steps.metadata.outputs.version }}"
```
