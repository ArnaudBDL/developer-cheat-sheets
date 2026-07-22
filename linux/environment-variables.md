# Linux : Environment Variables

## Inspect Variables

```bash
printenv
env
printenv PATH
echo "$HOME"
echo "$SHELL"
```

## Set and Export

```bash
NAME=value
export NAME=value
export PATH="$HOME/bin:$PATH"
unset NAME
```

## Command-Specific Environment

```bash
APP_ENV=production command
env APP_ENV=production command
env -i PATH=/usr/bin:/bin command
```

## Common Configuration Files

```text
/etc/environment
/etc/profile
/etc/profile.d/*.sh
~/.profile
~/.bash_profile
~/.bashrc
~/.zshrc
```

## Load a File

```bash
source ~/.bashrc
. /path/to/environment-file
```

Environment variables inherited by child processes may be visible to those processes. Do not expose secrets unnecessarily.
