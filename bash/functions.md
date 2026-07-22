# Bash : Functions

## Declare Functions

```bash
log() {
  printf '%s\n' "$*"
}

function warn {
  printf 'Warning: %s\n' "$*" >&2
}
```

## Arguments and Local Variables

```bash
greet() {
  local name="${1:?Name required}"
  local message="Hello ${name}"
  printf '%s\n' "$message"
}

greet "Arnaud"
```

## Return Status

```bash
is_readable_file() {
  local file="${1:?File required}"
  [[ -f "$file" && -r "$file" ]]
}

if is_readable_file config.env; then
  printf 'Readable\n'
fi
```

`return` returns an exit status from `0` to `255`, not arbitrary text.

## Return Data

```bash
get_version() {
  printf '%s\n' '1.0.0'
}

version="$(get_version)"
```

## Export and Remove

```bash
export -f function_name
unset -f function_name
declare -F
```
