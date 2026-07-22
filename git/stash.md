# Git : Stash

## Create a Stash

```bash
git stash push -m "Work in progress"
git stash push -u -m "Include untracked files"
git stash push -a -m "Include ignored files"
git stash push -p -m "Selected changes"
git stash push -- FILE
```

## List and Inspect

```bash
git stash list
git stash show stash@{0}
git stash show -p stash@{0}
```

## Apply

```bash
git stash apply
git stash apply stash@{1}
git stash pop
git stash branch recovered-work stash@{0}
```

## Remove

```bash
git stash drop stash@{0}
git stash clear
```

## Recover a Dropped Stash

```bash
git fsck --no-reflog --unreachable | grep commit
git show COMMIT
git stash store -m "Recovered stash" COMMIT
```
