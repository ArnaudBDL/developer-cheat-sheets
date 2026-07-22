# Visual Studio Code : Terminal

## Open and Manage

```text
Terminal: Create New Terminal
Terminal: Select Default Profile
Terminal: Split Terminal
Terminal: Rename the Active Terminal
Terminal: Kill the Active Terminal Instance
```

## Profile Example

```json
{
  "terminal.integrated.profiles.linux": {
    "bash-login": {
      "path": "/bin/bash",
      "args": ["-l"]
    }
  },
  "terminal.integrated.defaultProfile.linux": "bash-login"
}
```

## Rules

- The terminal inherits environment and workspace context.
- Do not paste unreviewed commands from untrusted content.
- Keep secrets out of shell history and task definitions.
- Verify shell profile startup scripts when terminal behavior differs from an external terminal.
- Use separate terminals for independent processes.
