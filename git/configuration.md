# Git : Configuration

## Identity

```bash
git config --global user.name "Arnaud BODEL"
git config --global user.email "email@example.com"
git config --global init.defaultBranch main
```

## Common Settings

```bash
git config --global core.editor "code --wait"
git config --global pull.rebase true
git config --global fetch.prune true
git config --global rerere.enabled true
git config --global color.ui auto
```

## Configuration Scopes

```bash
git config --system --list
git config --global --list
git config --local --list
git config --show-origin --list
git config --show-scope --list
```

## Read and Remove Values

```bash
git config --get user.name
git config --get-all remote.origin.fetch
git config --global --unset core.editor
git config --global --edit
```

## Conditional Includes

```ini
[includeIf "gitdir:~/Developer/Work/"]
    path = ~/.gitconfig-work
```
