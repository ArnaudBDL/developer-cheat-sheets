# Git : Commits

## Stage Changes

```bash
git add FILE
git add DIRECTORY/
git add .
git add -A
git add -p
git diff --staged
```

## Create Commits

```bash
git commit -m "Add feature"
git commit -am "Update tracked files"
git commit
git commit --allow-empty -m "Trigger pipeline"
```

## Amend

```bash
git commit --amend
git commit --amend -m "Corrected message"
git commit --amend --no-edit
```

## Inspect

```bash
git show HEAD
git show --stat HEAD
git log -1 --format=fuller
git diff HEAD~1 HEAD
```

## Sign Commits

```bash
git commit -S -m "Signed commit"
git log --show-signature -1
```
