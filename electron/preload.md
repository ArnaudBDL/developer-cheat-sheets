# Electron : Preload

## Expose a Narrow API

```javascript
const { contextBridge, ipcRenderer } = require('electron/renderer')

contextBridge.exposeInMainWorld('desktop', {
  openFile: () => ipcRenderer.invoke('dialog:open-file'),
  readTextFile: path => ipcRenderer.invoke('file:read-text', path),
  onUpdateStatus: callback => {
    const listener = (_event, status) => callback(status)
    ipcRenderer.on('update:status', listener)
    return () => ipcRenderer.removeListener('update:status', listener)
  }
})
```

## Rules

```text
Never expose ipcRenderer wholesale. Expose one method per approved capability, validate arguments in the main process, and avoid passing the IPC event object to renderer callbacks.
```

