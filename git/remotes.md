# Git : Remotes

## Inspect Remotes

```bash
git remote
git remote -v
git remote show origin
git config --get-regexp '^remote\.'
```

## Add and Update

```bash
git remote add origin REPOSITORY_URL
git remote add upstream UPSTREAM_URL
git remote set-url origin NEW_URL
git remote rename origin destination
git remote remove destination
```

## Fetch and Pull

```bash
git fetch origin
git fetch --all --prune
git pull --ff-only
git pull --rebase
git remote prune origin
```

## Push

```bash
git push -u origin main
git push origin BRANCH
git push --force-with-lease
git push origin --delete BRANCH
```

## Synchronize a Fork

```bash
git fetch upstream
git switch main
git merge --ff-only upstream/main
git push origin main
```
