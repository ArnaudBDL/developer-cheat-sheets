# GitHub Actions : Expressions

## Syntax

```yaml
${{ expression }}
```

## Conditions

```yaml
if: github.ref == 'refs/heads/main'
if: github.event_name == 'pull_request'
if: contains(github.event.pull_request.labels.*.name, 'deploy')
if: startsWith(github.ref, 'refs/tags/v')
```

## Status Functions

```yaml
if: success()
if: failure()
if: cancelled()
if: always()
```

## Common Functions

```yaml
${{ contains('Hello world', 'world') }}
${{ startsWith(github.ref, 'refs/tags/') }}
${{ endsWith(github.ref, '-beta') }}
${{ format('{0}-{1}', github.repository, github.run_number) }}
${{ fromJSON(inputs.matrix) }}
${{ toJSON(github.event) }}
${{ hashFiles('**/package-lock.json') }}
```

## Fallback Value

```yaml
env:
  TARGET: ${{ inputs.environment || 'staging' }}
```
