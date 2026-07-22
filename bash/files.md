# Bash : Files

## Test Paths

```bash
[[ -e "$path" ]]  # Exists
[[ -f "$path" ]]  # Regular file
[[ -d "$path" ]]  # Directory
[[ -L "$path" ]]  # Symbolic link
[[ -r "$path" ]]  # Readable
[[ -w "$path" ]]  # Writable
[[ -x "$path" ]]  # Executable
[[ -s "$path" ]]  # Non-empty
```

## Create and Manage

```bash
mkdir -p path/to/directory
touch file.txt
cp -- file.txt copy.txt
cp -a -- source/ destination/
mv -- source destination
rm -- file.txt
rm -rf -- directory
ln -s target link
```

## Read Files

```bash
cat file.txt
head -n 20 file.txt
tail -n 20 file.txt
tail -f application.log
sed -n '10,20p' file.txt
```

## Safe Line Reading

```bash
while IFS= read -r line || [[ -n "$line" ]]; do
  printf '%s\n' "$line"
done < file.txt
```

## Temporary Files

```bash
temporary_file="$(mktemp)"
temporary_directory="$(mktemp -d)"
trap 'rm -f "$temporary_file"; rm -rf "$temporary_directory"' EXIT
```

## Paths

```bash
script_directory="$(cd -- "$(dirname -- "${BASH_SOURCE[0]}")" && pwd)"
filename="$(basename -- "$path")"
directory="$(dirname -- "$path")"
```
