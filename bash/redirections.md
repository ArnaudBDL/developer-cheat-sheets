# Bash : Redirections

## Standard Streams

```text
0  standard input
1  standard output
2  standard error
```

## Output

```bash
command > output.txt
command >> output.txt
command 2> errors.txt
command 2>> errors.txt
command > output.txt 2> errors.txt
command > combined.txt 2>&1
command &> combined.txt
command >/dev/null 2>&1
```

## Input

```bash
command < input.txt
read -r line < input.txt
```

## Here Document

```bash
cat <<'EOF'
Variables are not expanded: $HOME
EOF

cat <<EOF
Variables are expanded: $HOME
EOF
```

## Here String

```bash
read -r first second <<< "one two"
grep 'pattern' <<< "$content"
```

## Custom File Descriptor

```bash
exec 3> output.log
printf '%s\n' "message" >&3
exec 3>&-

exec {log_fd}>>output.log
printf '%s\n' "message" >&"$log_fd"
exec {log_fd}>&-
```
