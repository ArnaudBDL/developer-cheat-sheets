# Electron : Architecture

## Process Model

```text
Main process     Application lifecycle, native APIs, windows and privileged operations
Renderer process UI running in Chromium
Preload script    Controlled bridge between renderer and privileged APIs
Utility process   Isolated process for selected background work
```

## Recommended Layout

```text
electron-app/
├── src/
│   ├── main.js
│   ├── preload.js
│   ├── renderer.js
│   └── index.html
├── package.json
└── assets/
```

## Trust Boundary

```text
Keep privileged operations in the main process. Expose narrow APIs through preload and contextBridge. Treat renderer input as untrusted.
```

