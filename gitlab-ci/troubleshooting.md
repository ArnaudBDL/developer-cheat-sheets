# GitLab CI : Troubleshooting

## Validate YAML

Use GitLab CI Lint to inspect syntax and the merged configuration produced by `include`, `extends` and defaults.

```bash
python - <<'PY'
import pathlib, yaml
yaml.safe_load(pathlib.Path('.gitlab-ci.yml').read_text())
print('YAML syntax is valid')
PY
```

## Enable Job Trace

Set the CI/CD variable only during controlled debugging:

```text
CI_DEBUG_TRACE=true
```

Debug traces can expose sensitive values and must be handled carefully.

## Common Problems

```text
Pipeline not created
  Check workflow:rules, event source and YAML validity.

Job skipped
  Check rules order, if expressions, changes and exists.

Job pending
  Check runner availability, tags, protection and capacity.

Job stuck
  Check runner health, executor, network and image pulls.

Artifact unavailable
  Check paths, expiration, needs and dependencies.

Cache miss
  Check key, path, policy and runner cache backend.

Variable empty
  Check name, scope, environment, protection and pipeline source.

Deployment blocked
  Check protected environment, approval and resource group.
```

## Runner Diagnostics

```bash
gitlab-runner --version
gitlab-runner list
gitlab-runner verify
gitlab-runner status
journalctl -u gitlab-runner -n 200
```

## Reduce Scope

Use a minimal job, a dedicated branch and explicit `rules` while isolating a pipeline problem.
