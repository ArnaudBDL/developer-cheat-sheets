# Git : Hooks

## Hook Location

```text
.git/hooks/
```

## Common Client Hooks

```text
pre-commit          Before a commit is created
prepare-commit-msg  Before the commit message editor opens
commit-msg          Validates the commit message
post-commit         After a commit is created
pre-rebase          Before a rebase begins
pre-push            Before objects are pushed
```

## pre-commit Example

```bash
#!/usr/bin/env bash
set -Eeuo pipefail

npm test
npm run lint
```

```bash
chmod +x .git/hooks/pre-commit
```

## commit-msg Example

```bash
#!/usr/bin/env bash
set -Eeuo pipefail

message_file="${1:?Commit message file required}"
pattern='^(feat|fix|docs|refactor|test|build|ci|chore)(\(.+\))?: .+'

grep -Eq "$pattern" "$message_file" || {
  printf 'Invalid commit message format
' >&2
  exit 1
}
```

## Shared Hooks Directory

```bash
git config core.hooksPath .githooks
chmod +x .githooks/*
```

Hooks are local by default and are not copied automatically when a repository is cloned.
