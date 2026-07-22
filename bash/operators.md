# Bash : Operators

## Command Operators

```bash
command_one && command_two   # Run second on success
command_one || command_two   # Run second on failure
command_one ; command_two    # Run sequentially
command &                    # Run in background
```

## String Operators

```bash
[[ "$left" == "$right" ]]
[[ "$left" != "$right" ]]
[[ "$value" == prefix* ]]
[[ "$value" =~ ^[0-9]+$ ]]
[[ -z "$value" ]]
[[ -n "$value" ]]
```

## Numeric Operators

```bash
((left == right))
((left != right))
((left < right))
((left <= right))
((left > right))
((left >= right))
((count++))
((total += value))
```

## Logical Operators

```bash
[[ condition_one && condition_two ]]
[[ condition_one || condition_two ]]
[[ ! condition ]]
((value > 0 && value < 10))
```

## File Operators

```bash
[[ -e "$path" ]]  # Exists
[[ -f "$path" ]]  # Regular file
[[ -d "$path" ]]  # Directory
[[ -r "$path" ]]  # Readable
[[ -w "$path" ]]  # Writable
[[ -x "$path" ]]  # Executable
[[ -s "$path" ]]  # Non-empty
[[ "$a" -nt "$b" ]] # Newer than
```
