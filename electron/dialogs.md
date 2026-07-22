# Electron : Dialogs

## Open File

```javascript
ipcMain.handle('dialog:open-file', async event => {
  const window = BrowserWindow.fromWebContents(event.sender)
  const result = await dialog.showOpenDialog(window, {
    properties: ['openFile'],
    filters: [{ name: 'Text', extensions: ['txt', 'md'] }]
  })

  if (result.canceled) return null
  return { path: result.filePaths[0] }
})
```

## Save and Message

```javascript
const save = await dialog.showSaveDialog(window, {
  defaultPath: 'document.txt'
})

await dialog.showMessageBox(window, {
  type: 'warning',
  message: 'Unsaved changes',
  buttons: ['Cancel', 'Discard'],
  defaultId: 0,
  cancelId: 0
})
```

