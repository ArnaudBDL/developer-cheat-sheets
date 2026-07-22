# Git : Repositories

## Create and Clone

```bash
git init
git init --initial-branch=main
git clone REPOSITORY_URL
git clone --depth 1 REPOSITORY_URL
git clone --branch BRANCH REPOSITORY_URL
git clone REPOSITORY_URL DIRECTORY
```

## Repository States

```text
Working tree  Files currently checked out
Index         Staging area for the next commit
Repository    Committed objects and references inside .git
```

## Inspect

```bash
git status
git status --short
git rev-parse --show-toplevel
git rev-parse --is-inside-work-tree
git count-objects -vH
```

## Ignore Files

```gitignore
.env
node_modules/
vendor/
dist/
coverage/
*.log
```

```bash
git check-ignore -v FILE
git ls-files --others --ignored --exclude-standard
```

## Bare Repository

```bash
git init --bare project.git
git clone --bare REPOSITORY_URL
```
