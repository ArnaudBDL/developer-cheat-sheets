# Bash : Debugging

## Syntax Check

```bash
bash -n script.sh
```

## Execution Trace

```bash
bash -x script.sh
bash -x script.sh argument

set -x
command
set +x
```

## Detailed Trace Prefix

```bash
export PS4='+ ${BASH_SOURCE}:${LINENO}:${FUNCNAME[0]}: '
bash -x script.sh
```

## Trace to a File Descriptor

```bash
exec 9>trace.log
export BASH_XTRACEFD=9
set -x
command
set +x
exec 9>&-
```

## Inspect State

```bash
declare -p variable
declare -p array_name
typeset -p variable
printf 'status=%d line=%d function=%s\n' "$?" "$LINENO" "${FUNCNAME[0]}"
```

## Error Trace

```bash
set -E
trap 'printf "Error: %s:%s in %s, status %s\n" \
  "${BASH_SOURCE[0]}" "$LINENO" "${FUNCNAME[0]:-main}" "$?" >&2' ERR
```

## Static Analysis

```bash
shellcheck script.sh
shellcheck -x script.sh
shfmt -d script.sh
shfmt -w script.sh
```

Avoid enabling `set -x` around secrets because expanded commands can expose sensitive values.
