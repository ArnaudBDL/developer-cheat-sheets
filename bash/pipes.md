# Bash : Pipes

## Basic Pipeline

```bash
printf '%s\n' one two three | grep 't'
ps aux | grep '[n]ginx'
find . -type f -name '*.md' -print0 | xargs -0 grep -n 'pattern'
```

## Pipeline Status

```bash
set -o pipefail
command_one | command_two | command_three
status=$?
printf '%d\n' "$status"
printf '%s\n' "${PIPESTATUS[@]}"
```

Without `pipefail`, a pipeline normally returns the status of its last command.

## Pipe Standard Error

```bash
command 2>&1 | tee output.log
command |& tee output.log
```

## tee

```bash
command | tee output.log
command | tee -a output.log
command | tee >(grep ERROR > errors.log) >(grep WARN > warnings.log) >/dev/null
```

## Avoid a Pipeline Subshell

```bash
count=0
while IFS= read -r line; do
  ((count++))
done < <(generate_lines)
```
