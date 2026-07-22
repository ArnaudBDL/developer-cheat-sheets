# Bash : Loops

## for Loop

```bash
for item in one two three; do
  printf '%s\n' "$item"
done

for file in *.md; do
  [[ -e "$file" ]] || continue
  printf '%s\n' "$file"
done
```

## C-Style Loop

```bash
for ((index = 0; index < 10; index++)); do
  printf '%d\n' "$index"
done
```

## while Loop

```bash
count=0
while ((count < 5)); do
  printf '%d\n' "$count"
  ((count++))
done
```

## Read a File Safely

```bash
while IFS= read -r line || [[ -n "$line" ]]; do
  printf '%s\n' "$line"
done < file.txt
```

## until Loop

```bash
until curl --fail --silent http://localhost:8080/health >/dev/null; do
  sleep 2
done
```

## Control

```bash
continue
continue 2
break
break 2
```
