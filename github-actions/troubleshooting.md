# GitHub Actions : Troubleshooting

## Workflow Runs

```bash
gh workflow list
gh run list --limit 20
gh run view RUN_ID
gh run view RUN_ID --log
gh run watch RUN_ID
gh run rerun RUN_ID
gh run rerun RUN_ID --failed
```

## Enable Debug Logging

Set repository or organization secrets:

```text
ACTIONS_RUNNER_DEBUG=true
ACTIONS_STEP_DEBUG=true
```

## Inspect Contexts

```yaml
- name: Inspect GitHub context
  env:
    CONTEXT: ${{ toJSON(github) }}
  run: printf '%s
' "$CONTEXT"
```

Avoid printing contexts that may contain sensitive data.

## Common Problems

```text
Workflow does not start
  Check file location, YAML syntax, event filters and branch or path rules.

Job remains queued
  Check runner availability, labels, concurrency and organization policy.

Permission denied
  Check permissions, environment protection and token scope.

Secret is empty
  Check secret name, scope, environment and fork restrictions.

Cache not restored
  Check path, key, lock-file hash and runner operating system.

Artifact missing
  Check upload path, conditional steps and job dependencies.

Expression error
  Check context availability, quoting and fromJSON input.
```

## Local Checks

```bash
yamllint .github/workflows/
gh workflow view WORKFLOW
```
