# Bash : Processes

## Background Processes

```bash
long_command &
pid=$!
printf 'PID: %d\n' "$pid"
wait "$pid"
status=$?
```

## Jobs

```bash
jobs
jobs -l
fg %1
bg %1
wait
```

## Signals

```bash
kill PID
kill -TERM PID
kill -INT PID
kill -KILL PID
kill -0 PID
```

## Process Information

```bash
printf 'Current shell PID: %s\n' "$$"
printf 'Parent PID: %s\n' "$PPID"
printf 'Last background PID: %s\n' "$!"
ps -p "$pid" -o pid,ppid,stat,etime,command
```

## Subshell and exec

```bash
(cd /tmp && command)
exec command
```

## Process Substitution

```bash
diff <(sort file-a.txt) <(sort file-b.txt)
while IFS= read -r line; do
  printf '%s\n' "$line"
done < <(generate_lines)
```
