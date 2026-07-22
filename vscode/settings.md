# Visual Studio Code : Settings

## Scopes

```text
Default settings
User settings
Remote settings
Workspace settings
Workspace-folder settings in multi-root workspaces
Language-specific settings
```

## settings.json

```json
{
  "editor.formatOnSave": true,
  "editor.tabSize": 2,
  "files.trimTrailingWhitespace": true,
  "terminal.integrated.defaultProfile.osx": "zsh"
}
```

## Language Override

```json
{
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true
  }
}
```

Use User settings for personal preferences and Workspace settings for shared project behavior. Review Workspace Trust before allowing repository settings to influence extension or task execution.
