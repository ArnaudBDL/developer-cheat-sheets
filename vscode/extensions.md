# Visual Studio Code : Extensions

## CLI

```bash
code --list-extensions
code --show-versions
code --install-extension publisher.extension
code --uninstall-extension publisher.extension
code --install-extension extension.vsix
```

## Recommendations

```json
{
  "recommendations": [
    "dbaeumer.vscode-eslint"
  ],
  "unwantedRecommendations": []
}
```

## Controls

- Review publisher, permissions, trust and update history.
- Install only extensions needed for the workspace.
- Disable an extension globally or only for the current workspace.
- Use approved VSIX distribution in restricted environments.
- Reproduce problems with extensions disabled before blaming the core editor.
- Keep extension recommendations in `.vscode/extensions.json`.
