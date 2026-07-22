# Visual Studio Code : Troubleshooting

## Baseline

```bash
code --version
code --status
code --disable-extensions
code --verbose
```

## Commands

```text
Developer: Reload Window
Developer: Restart Extension Host
Developer: Show Running Extensions
Developer: Open Logs Folder
Developer: Toggle Developer Tools
Help: Start Extension Bisect
Profiles: Create an Empty Profile
```

## Checks

```text
Reproduce with extensions disabled.
Test with an empty profile.
Check workspace trust and workspace settings.
Inspect extension-host, window, terminal and remote logs.
Verify shell PATH and environment inheritance.
Check remote connectivity and disk permissions.
Recreate generated .vscode configuration only after backing it up.
```

For debugging failures, confirm the correct debugger extension, active configuration, program path, runtime and `launch.json`. Preserve logs and exact reproduction steps without including secrets.
