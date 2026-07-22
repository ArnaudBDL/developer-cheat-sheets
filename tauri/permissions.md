# Tauri : Permissions

## Permission Concept

```text
A permission identifies an operation exposed by Tauri core, an application command or a plugin. Permissions are referenced by capabilities rather than granted globally.
```

## Generate and List

```bash
npm run tauri permission new application-read-settings
npm run tauri permission ls
npm run tauri permission add fs:allow-read-text-file
npm run tauri permission rm fs:allow-read-text-file
```

## Application Command Permission

```toml
[[permission]]
identifier = "allow-load-settings"
description = "Allows the load_settings command"
commands.allow = ["load_settings"]

[[permission]]
identifier = "deny-load-settings"
description = "Denies the load_settings command"
commands.deny = ["load_settings"]
```

