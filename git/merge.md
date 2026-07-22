# Git : Merge

## Merge a Branch

```bash
git switch main
git fetch origin
git pull --ff-only
git merge feature/name
```

## Merge Modes

```bash
git merge --ff-only feature/name
git merge --no-ff feature/name
git merge --squash feature/name
git merge --no-commit feature/name
```

## Resolve Conflicts

```bash
git status
git diff --name-only --diff-filter=U
git checkout --ours FILE
git checkout --theirs FILE
git add FILE
git commit
```

## Abort or Continue

```bash
git merge --abort
git merge --continue
```

## Inspect Merge

```bash
git log --graph --oneline --decorate --all
git show --cc HEAD
git diff ORIG_HEAD HEAD
```
