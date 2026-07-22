# Tauri : Plugins

## Add a Plugin

```bash
npm run tauri add fs
npm run tauri add dialog
npm run tauri add updater
```

## Register Manually

```rust
tauri::Builder::default()
    .plugin(tauri_plugin_fs::init())
    .plugin(tauri_plugin_dialog::init())
    .run(tauri::generate_context!())
    .expect("error while running Tauri application");
```

## Plugin Anatomy

```text
Rust crate       Native plugin implementation
NPM package      Optional frontend bindings
permissions      Plugin command permissions
capabilities     Application grants referencing permissions
```

## Manage Plugins

```bash
npm run tauri add PLUGIN
npm run tauri remove PLUGIN
npm run tauri plugin new PLUGIN_NAME
```

