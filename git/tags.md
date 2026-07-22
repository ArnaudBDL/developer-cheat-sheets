# Git : Tags

## List and Inspect

```bash
git tag
git tag --list 'v1.*'
git show v1.0.0
git for-each-ref refs/tags --format='%(refname:short) %(creatordate:short)'
```

## Create Tags

```bash
git tag v1.0.0
git tag -a v1.0.0 -m "Release 1.0.0"
git tag -s v1.0.0 -m "Signed release 1.0.0"
git tag -a v1.0.0 COMMIT -m "Release 1.0.0"
```

## Push Tags

```bash
git push origin v1.0.0
git push origin --tags
git push --follow-tags
```

## Delete Tags

```bash
git tag -d v1.0.0
git push origin --delete v1.0.0
```

## Verify

```bash
git tag -v v1.0.0
git show --show-signature v1.0.0
```
