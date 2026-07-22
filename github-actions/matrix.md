# GitHub Actions : Matrix

## Basic Matrix

```yaml
jobs:
  test:
    strategy:
      matrix:
        os: [ubuntu-latest, macos-latest]
        node: ['20', '22']
    runs-on: ${{ matrix.os }}
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node }}
      - run: npm test
```

## Include and Exclude

```yaml
strategy:
  matrix:
    os: [ubuntu-latest, windows-latest]
    node: ['20', '22']
    exclude:
      - os: windows-latest
        node: '20'
    include:
      - os: macos-latest
        node: '22'
        experimental: true
```

## Failure and Parallelism

```yaml
strategy:
  fail-fast: false
  max-parallel: 3
  matrix:
    node: ['20', '22', '24']
```

## Dynamic Matrix

```yaml
strategy:
  matrix: ${{ fromJSON(needs.prepare.outputs.matrix) }}
```
