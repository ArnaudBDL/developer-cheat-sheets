# Bash : Arguments

## Positional Parameters

```bash
printf 'Script: %s\n' "$0"
printf 'First: %s\n' "${1:-}"
printf 'Second: %s\n' "${2:-}"
printf 'Count: %s\n' "$#"
printf 'All: %s\n' "$*"
```

## Preserve Argument Boundaries

```bash
for argument in "$@"; do
  printf '%s\n' "$argument"
done
```

Use `"$@"` when forwarding arguments.

```bash
run_command() {
  command_name "$@"
}
```

## Shift Arguments

```bash
while (($# > 0)); do
  printf '%s\n' "$1"
  shift
done
```

## Parse Options with getopts

```bash
verbose=false
output=""

while getopts ':vo:' option; do
  case "$option" in
    v) verbose=true ;;
    o) output="$OPTARG" ;;
    :) printf 'Missing value for -%s\n' "$OPTARG" >&2; exit 2 ;;
    \?) printf 'Unknown option: -%s\n' "$OPTARG" >&2; exit 2 ;;
  esac
done
shift $((OPTIND - 1))
```

## Require Arguments

```bash
input="${1:?Usage: script.sh INPUT}"
```
