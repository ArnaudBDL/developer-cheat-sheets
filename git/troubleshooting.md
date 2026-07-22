# Git : Troubleshooting

## Repository State

```bash
git status
git status --short --branch
git log --oneline --graph --decorate --all -20
git reflog -20
git remote -v
```

## Authentication and Remote

```bash
git remote show origin
git ls-remote origin
ssh -T git@HOST
ssh -vT git@HOST
GIT_CURL_VERBOSE=1 git fetch origin
```

## Merge or Rebase in Progress

```bash
git status
git diff --name-only --diff-filter=U
git merge --abort
git rebase --continue
git rebase --abort
git cherry-pick --abort
```

## Non-Fast-Forward Push

```bash
git fetch origin
git log --oneline --graph --decorate HEAD origin/BRANCH
git rebase origin/BRANCH
git push --force-with-lease
```

## Detached HEAD

```bash
git status
git switch -c recovered-work
git switch main
```

## Repository Integrity

```bash
git fsck --full
git count-objects -vH
git gc
git maintenance run
```

## Trace Git

```bash
GIT_TRACE=1 git COMMAND
GIT_TRACE_PACKET=1 GIT_TRACE=1 git fetch
GIT_CURL_VERBOSE=1 git fetch
```
