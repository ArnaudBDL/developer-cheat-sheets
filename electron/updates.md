# Electron : Updates

## Update Events

```javascript
autoUpdater.on('checking-for-update', () => sendStatus('checking'))
autoUpdater.on('update-available', info => sendStatus('available', info))
autoUpdater.on('update-not-available', info => sendStatus('current', info))
autoUpdater.on('error', error => sendStatus('error', error.message))
autoUpdater.on('download-progress', progress => sendStatus('progress', progress))
autoUpdater.on('update-downloaded', info => sendStatus('downloaded', info))
```

## Check and Install

```javascript
app.whenReady().then(() => {
  autoUpdater.checkForUpdates()
})

ipcMain.handle('update:install', () => {
  autoUpdater.quitAndInstall()
})
```

## Rules

```text
Use a trusted update source and signed releases. Surface update state without exposing autoUpdater directly to the renderer. Test update paths from previously released builds.
```

