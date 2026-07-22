# Visual Studio Code : Snippets

## User Snippet

```json
{
  "Console log": {
    "scope": "javascript,typescript",
    "prefix": "clg",
    "body": [
      "console.log(${1:value});",
      "$0"
    ],
    "description": "Insert console.log"
  }
}
```

## Placeholders

```text
$1, $2     Tab stops
${1:name}  Placeholder with default text
${1|a,b|}  Choice
$0         Final cursor position
```

Create language snippets, global snippets or project snippets. Keep prefixes distinctive, avoid embedding secrets, and use project snippets only for conventions valuable to the repository.
