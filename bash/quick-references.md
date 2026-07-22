# Bash : Quick References

## Script header

```bash
#!/usr/bin/env bash
set -Eeuo pipefail
IFS=$'\n\t'
```

## Variables and tests

```bash
name="value"
readonly name

if [[ -f "$file" ]]; then
  echo "File exists"
fi

[[ -n "$value" ]] && echo "$value"
```

## Functions and loops

```bash
function log() {
  printf '%s\n' "$*"
}

for item in "$@"; do
  log "$item"
done
```

## Debugging

```bash
bash -n script.sh
bash -x script.sh
shellcheck script.sh
```
