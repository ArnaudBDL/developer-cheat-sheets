# Bash : Scripting

## Reliable Script Template

```bash
#!/usr/bin/env bash
set -Eeuo pipefail
IFS=$'\n\t'

readonly SCRIPT_NAME="$(basename -- "$0")"
readonly SCRIPT_DIR="$(cd -- "$(dirname -- "${BASH_SOURCE[0]}")" && pwd)"

usage() {
  cat <<EOF
Usage: ${SCRIPT_NAME} [OPTIONS] INPUT

Options:
  -v          Enable verbose output
  -h          Show help
EOF
}

die() {
  printf 'Error: %s\n' "$*" >&2
  exit 1
}

main() {
  local verbose=false

  while getopts ':vh' option; do
    case "$option" in
      v) verbose=true ;;
      h) usage; return 0 ;;
      \?) die "Unknown option: -${OPTARG}" ;;
    esac
  done
  shift $((OPTIND - 1))

  local input="${1:?Usage: ${SCRIPT_NAME} [OPTIONS] INPUT}"
  "$verbose" && printf 'Input: %s\n' "$input"
}

main "$@"
```

## Make Executable

```bash
chmod +x script.sh
./script.sh
bash script.sh
```

## Source a Library

```bash
source "${SCRIPT_DIR}/lib/logging.sh"
# Equivalent shorthand
. "${SCRIPT_DIR}/lib/logging.sh"
```

## Style Rules

- Quote parameter expansions unless splitting or globbing is intentional.
- Use `printf` instead of relying on implementation-specific `echo` behavior.
- Use `local` inside functions.
- Pass script arguments with `main "$@"`.
- Validate commands, arguments and paths before destructive operations.
- Use `--` before path operands when the command supports it.
- Prefer arrays for command construction.
