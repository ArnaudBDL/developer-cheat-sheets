# GitHub Actions : Cache

## Node.js Cache

```yaml
- uses: actions/setup-node@v4
  with:
    node-version: '22'
    cache: npm
    cache-dependency-path: package-lock.json
```

## Generic Cache

```yaml
- uses: actions/cache@v4
  with:
    path: ~/.cache/example
    key: ${{ runner.os }}-example-${{ hashFiles('**/lockfile') }}
    restore-keys: |
      ${{ runner.os }}-example-
```

## Cache Hit

```yaml
- id: cache
  uses: actions/cache@v4
  with:
    path: .cache
    key: ${{ runner.os }}-${{ hashFiles('**/package-lock.json') }}

- if: steps.cache.outputs.cache-hit != 'true'
  run: ./prepare-cache.sh
```

## Rules

- Build cache keys from the operating system, toolchain and lock files.
- Do not cache credentials or sensitive content.
- Use artifacts, not cache, for required build outputs.
- Keep restore keys broad enough for reuse but narrow enough to avoid incompatible content.
