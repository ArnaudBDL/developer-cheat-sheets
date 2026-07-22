# Bash : Syntax

## Script Header

```bash
#!/usr/bin/env bash
set -Eeuo pipefail
IFS=$'\n\t'
```

## Comments and Commands

```bash
# Single-line comment
printf '%s\n' "Hello"
command_one; command_two
command_one && command_two
command_one || fallback_command
```

## Quoting

```bash
name="Arnaud"
printf '%s\n' "$name"       # Expands variables
printf '%s\n' '$name'       # Literal text
printf '%s\n' "${name}"     # Explicit boundary
printf '%s\n' $'line 1\nline 2'
```

## Expansions

```bash
files=(file-{1..5}.txt)       # Brace expansion
home_directory=~             # Tilde expansion
current_date="$(date +%F)"   # Command substitution
result=$((10 + 5))           # Arithmetic expansion
for file in *.md; do         # Filename expansion
  printf '%s\n' "$file"
done
```

## Command Groups

```bash
{ command_one; command_two; } # Current shell
(command_one; command_two)    # Subshell
```
