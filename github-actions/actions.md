# GitHub Actions : Actions

## Use an Action

```yaml
- uses: actions/checkout@v4
- uses: actions/setup-node@v4
  with:
    node-version: '22'
```

## Action References

```text
owner/repository@tag
owner/repository@commit-sha
./relative/path/to/action
```

Pin third-party actions to a trusted full commit SHA when stronger supply-chain control is required.

## Composite Action Metadata

```yaml
name: Build application
description: Install dependencies and build
inputs:
  node-version:
    required: false
    default: '22'
runs:
  using: composite
  steps:
    - uses: actions/setup-node@v4
      with:
        node-version: ${{ inputs.node-version }}
    - run: npm ci
      shell: bash
    - run: npm run build
      shell: bash
```

## Local Action

```yaml
- uses: actions/checkout@v4
- uses: ./.github/actions/build
```
