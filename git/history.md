# Git : History

## Log

```bash
git log
git log --oneline
git log --oneline --graph --decorate --all
git log --stat
git log -p
git log --since='2 weeks ago'
git log --author='NAME'
git log --grep='pattern'
```

## File History

```bash
git log -- FILE
git log --follow -- FILE
git log -p -- FILE
git blame FILE
git blame -L 10,30 FILE
```

## Inspect Objects

```bash
git show COMMIT
git show COMMIT:PATH
git cat-file -t OBJECT
git cat-file -p OBJECT
```

## Search History

```bash
git log -S 'exact text' --all
git log -G 'regular expression' --all
git grep 'pattern' COMMIT
```

## Reflog and Bisect

```bash
git reflog
git bisect start
git bisect bad
git bisect good GOOD_COMMIT
git bisect reset
```
