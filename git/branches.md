# Git : Branches

## List Branches

```bash
git branch
git branch -a
git branch -vv
git branch --merged
git branch --no-merged
```

## Create and Switch

```bash
git branch feature/name
git switch feature/name
git switch -c feature/name
git switch -c feature/name origin/feature/name
git switch -
```

## Rename and Delete

```bash
git branch -m old-name new-name
git branch -m new-name
git branch -d feature/name
git branch -D feature/name
git push origin --delete feature/name
```

## Tracking

```bash
git branch --set-upstream-to=origin/main main
git push -u origin feature/name
git branch --unset-upstream
```

## Compare Branches

```bash
git log main..feature/name
git diff main...feature/name
git merge-base main feature/name
```
