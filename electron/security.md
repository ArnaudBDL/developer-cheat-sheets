# Electron : Security

## Secure WebPreferences

```javascript
webPreferences: {
  preload: path.join(__dirname, 'preload.js'),
  contextIsolation: true,
  nodeIntegration: false,
  sandbox: true,
  webSecurity: true
}
```

## Navigation Control

```javascript
mainWindow.webContents.setWindowOpenHandler(({ url }) => {
  return isTrustedExternalUrl(url) ? { action: 'allow' } : { action: 'deny' }
})

mainWindow.webContents.on('will-navigate', (event, url) => {
  if (!isTrustedNavigation(url)) event.preventDefault()
})
```

## Checklist

```text
Keep Electron and dependencies current. Load only trusted content. Use context isolation and sandboxing. Keep Node integration disabled in renderers. Define a restrictive Content Security Policy. Validate IPC senders and payloads. Do not expose Electron or Node APIs directly. Review permissions, navigation and new-window requests.
```

