# Electron : Ipc

## Renderer to Main

```javascript
// main.js
ipcMain.handle('settings:load', async event => {
  validateSender(event.senderFrame)
  return loadSettings()
})

// preload.js
contextBridge.exposeInMainWorld('settings', {
  load: () => ipcRenderer.invoke('settings:load')
})
```

## Main to Renderer

```javascript
// main.js
window.webContents.send('application:status', { ready: true })

// preload.js
contextBridge.exposeInMainWorld('application', {
  onStatus: callback => {
    const listener = (_event, status) => callback(status)
    ipcRenderer.on('application:status', listener)
    return () => ipcRenderer.removeListener('application:status', listener)
  }
})
```

## Validation

```javascript
function validateSender(frame) {
  const url = new URL(frame.url)
  if (url.protocol !== 'file:') {
    throw new Error('Untrusted IPC sender')
  }
}
```

