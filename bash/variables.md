# Bash : Variables

## Assign and Read

```bash
name="value"
printf '%s\n' "$name"
printf '%s\n' "${name}"
```

Do not add spaces around `=` during assignment.

## Declare Variables

```bash
declare variable="value"
declare -r constant="value"
declare -i count=10
declare -l lowercase="VALUE"
declare -u uppercase="value"
readonly application_name="my-app"
local local_value="value"
```

## Parameter Expansion

```bash
value="${variable:-default}"      # Default if unset or empty
value="${variable-default}"       # Default if unset
value="${variable:=default}"      # Assign default
required="${variable:?Required}"  # Stop if missing
length="${#variable}"
trimmed="${variable#prefix}"
replaced="${variable/search/replace}"
```

## Environment Variables

```bash
export APP_ENV="production"
APP_ENV="test" command
printenv APP_ENV
unset APP_ENV
```

## Command Substitution

```bash
current_directory="$(pwd)"
first_line="$(head -n 1 file.txt)"
```
