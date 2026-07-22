# Linux : Processes

## List Processes

```bash
ps aux
ps -ef
ps -eo pid,ppid,user,state,%cpu,%mem,command --sort=-%cpu
pstree -p
top
```

## Find Processes

```bash
pgrep process-name
pgrep -af process-name
pidof process-name
```

## Signals

```bash
kill -TERM PID
kill -KILL PID
kill -HUP PID
pkill -TERM process-name
kill -l
```

Use `SIGTERM` before `SIGKILL` so the process can shut down cleanly when supported.

## Priority

```bash
nice -n 10 command
renice 10 -p PID
```

## Background Jobs

```bash
command &
jobs
fg %1
bg %1
nohup command > application.log 2>&1 &
disown
```

## Inspect Resources

```bash
cat /proc/PID/status
lsof -p PID
strace -p PID
```
