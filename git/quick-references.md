# Git : Quick References

## Repository

```bash
git init
git clone REPOSITORY_URL
git status
git add .
git commit -m "message"
```

## Branches

```bash
git branch
git switch -c feature/name
git switch main
git merge feature/name
git branch -d feature/name
```

## History and recovery

```bash
git log --oneline --graph --decorate --all
git diff
git restore FILE
git reset HEAD~1
git revert COMMIT
git reflog
```

## Remote

```bash
git remote -v
git fetch --all --prune
git pull --rebase
git push -u origin BRANCH
```
