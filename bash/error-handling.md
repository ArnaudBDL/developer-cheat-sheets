# Bash : Error Handling

## Strict Mode

```bash
set -Eeuo pipefail
IFS=$'\n\t'
```

- `-e`: exits after an unhandled failing command.
- `-E`: propagates the `ERR` trap into functions and subshell contexts.
- `-u`: treats unset parameters as errors.
- `pipefail`: makes a pipeline fail when one of its commands fails.

## Check Commands Explicitly

```bash
if ! command; then
  printf 'Command failed\n' >&2
  exit 1
fi

command || {
  status=$?
  printf 'Command failed with status %d\n' "$status" >&2
  exit "$status"
}
```

## Error Function

```bash
die() {
  printf 'Error: %s\n' "$*" >&2
  exit 1
}

[[ -f "$file" ]] || die "File not found: $file"
```

## Traps

```bash
cleanup() {
  rm -f -- "${temporary_file:-}"
}

on_error() {
  local status=$?
  printf 'Failure at line %s with status %s\n' "$1" "$status" >&2
  exit "$status"
}

trap cleanup EXIT
trap 'on_error "$LINENO"' ERR
trap 'exit 130' INT
trap 'exit 143' TERM
```

## Validate Requirements

```bash
command -v docker >/dev/null 2>&1 || die "docker is required"
input="${1:?Usage: script.sh INPUT}"
```
