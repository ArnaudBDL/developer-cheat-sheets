# Git : Rebase

## Rebase onto a Branch

```bash
git switch feature/name
git fetch origin
git rebase origin/main
```

## Interactive Rebase

```bash
git rebase -i HEAD~5
git rebase -i --root
```

```text
pick    Keep commit
reword  Change commit message
edit    Stop to modify commit
squash  Combine with previous commit and edit message
fixup   Combine with previous commit and discard message
drop    Remove commit
```

## Conflicts

```bash
git status
# Resolve files
git add FILE
git rebase --continue
git rebase --skip
git rebase --abort
```

## Rebase and Push

```bash
git push --force-with-lease
```

Prefer `--force-with-lease` over `--force`. Avoid rebasing shared history unless the team workflow explicitly allows it.

## Autosquash

```bash
git commit --fixup COMMIT
git rebase -i --autosquash BASE
```
