# Bash : Arrays

## Indexed Arrays

```bash
items=(one two "three words")
items+=(four)
items[0]="first"

printf '%s\n' "${items[0]}"
printf '%s\n' "${items[@]}"
printf 'Count: %d\n' "${#items[@]}"
printf 'Indexes: %s\n' "${!items[@]}"
```

## Iterate

```bash
for item in "${items[@]}"; do
  printf '%s\n' "$item"
done

for index in "${!items[@]}"; do
  printf '%s = %s\n' "$index" "${items[$index]}"
done
```

## Slices and Removal

```bash
subset=("${items[@]:1:2}")
unset 'items[1]'
items=()
```

## Associative Arrays

```bash
declare -A configuration=(
  [environment]="production"
  [port]="8080"
)

configuration[host]="localhost"
printf '%s\n' "${configuration[environment]}"

for key in "${!configuration[@]}"; do
  printf '%s=%s\n' "$key" "${configuration[$key]}"
done
```

## Read into an Array

```bash
mapfile -t lines < file.txt
read -r -a words <<< "one two three"
```
