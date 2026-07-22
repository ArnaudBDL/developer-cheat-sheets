# Linux : Files and Directories

## Navigate and List

```bash
pwd
ls
ls -lah
ls -l --time-style=long-iso
cd /path/to/directory
cd -
```

## Create, Copy, Move and Remove

```bash
touch file.txt
mkdir directory
mkdir -p path/to/directory
cp source.txt destination.txt
cp -a source/ destination/
mv old-name new-name
rm file.txt
rm -r directory/
```

## Read Files

```bash
cat file.txt
less file.txt
head -n 20 file.txt
tail -n 20 file.txt
tail -f application.log
```

## Find Content and Files

```bash
find /path -type f -name '*.log'
find /path -type f -mtime -7
grep -Rni 'pattern' /path
command -v executable
whereis executable
```

## Links

```bash
ln source hard-link
ln -s /target/path symbolic-link
readlink symbolic-link
readlink -f symbolic-link
```

## Archive

```bash
tar -czf archive.tar.gz directory/
tar -xzf archive.tar.gz
tar -tf archive.tar.gz
```
