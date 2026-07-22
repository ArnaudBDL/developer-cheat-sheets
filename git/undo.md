# Git : Undo

## Discard Working-Tree Changes

```bash
git restore FILE
git restore --source=HEAD -- FILE
git restore .
```

These commands discard uncommitted changes from the working tree.

## Unstage Changes

```bash
git restore --staged FILE
git reset HEAD FILE
```

## Undo the Last Commit

```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```

```text
--soft   Move HEAD, keep changes staged
--mixed  Move HEAD, keep changes unstaged
--hard   Move HEAD and discard working-tree and index changes
```

## Revert Published History

```bash
git revert COMMIT
git revert --no-commit COMMIT
git revert -m 1 MERGE_COMMIT
```

## Recover with Reflog

```bash
git reflog
git show HEAD@{1}
git switch -c recovery HEAD@{1}
git reset --hard HEAD@{1}
```

## Clean Untracked Files

```bash
git clean -n
git clean -nd
git clean -f
git clean -fd
```

Always preview `git clean` and destructive reset operations first.
