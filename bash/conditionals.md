# Bash : Conditionals

## if, elif and else

```bash
if [[ -f "$file" ]]; then
  printf 'File exists\n'
elif [[ -d "$file" ]]; then
  printf 'Directory exists\n'
else
  printf 'Path not found\n'
fi
```

## Command Status

```bash
if command -v docker >/dev/null 2>&1; then
  docker --version
fi

if ! grep -q 'pattern' file.txt; then
  printf 'Pattern not found\n'
fi
```

## Arithmetic Condition

```bash
if ((count >= 10)); then
  printf 'Limit reached\n'
fi
```

## case

```bash
case "$environment" in
  development|test)
    debug=true
    ;;
  production)
    debug=false
    ;;
  *)
    printf 'Unknown environment: %s\n' "$environment" >&2
    exit 2
    ;;
esac
```

## Pattern Matching

```bash
case "$filename" in
  *.tar.gz) printf 'Compressed archive\n' ;;
  *.md)     printf 'Markdown file\n' ;;
  *)        printf 'Other file\n' ;;
esac
```
