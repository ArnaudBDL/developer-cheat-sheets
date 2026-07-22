# Electron : Troubleshooting

## Run with Logging

```bash
npm start -- --enable-logging
ELECTRON_ENABLE_LOGGING=1 npm start
ELECTRON_ENABLE_STACK_DUMPING=1 npm start
```

## Development Tools

```javascript
mainWindow.webContents.openDevTools({ mode: 'detach' })
console.log(process.versions)
console.log(app.getPath('logs'))
```

## Common Problems

```text
Blank window: inspect loadFile or loadURL, preload path, DevTools console and CSP.
Preload API missing: check preload execution, contextBridge name and contextIsolation.
IPC handler not found: confirm channel spelling and handler registration before renderer calls.
Native module failure: rebuild the module for the Electron ABI.
Packaged path failure: use app.getAppPath(), process.resourcesPath and path.join().
Update failure: inspect signing, feed configuration, release metadata and updater events.
```

## Process Failures

```javascript
app.on('child-process-gone', (_event, details) => {
  console.error('Child process gone', details)
})

mainWindow.webContents.on('render-process-gone', (_event, details) => {
  console.error('Renderer gone', details)
})
```

