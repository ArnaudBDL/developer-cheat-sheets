# Tauri : Project Structure

## Typical Structure

```text
application/
├── src/                     Frontend source
├── public/                  Frontend static assets
├── package.json
└── src-tauri/
    ├── capabilities/        Capability files
    ├── icons/               Application icons
    ├── src/
    │   ├── lib.rs           Tauri application setup
    │   └── main.rs          Desktop entry point
    ├── Cargo.toml           Rust dependencies
    ├── build.rs             Tauri build script
    └── tauri.conf.json      Application configuration
```

## Responsibilities

```text
Frontend       Interface and browser-side logic
src-tauri      Native application, commands, plugins and configuration
capabilities   Window and webview access boundaries
permissions    Individual operations granted through capabilities
```

