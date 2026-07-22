# PowerShell : Error Handling

## try, catch and finally

```powershell
try {
    $content = Get-Content -LiteralPath './config.json' -ErrorAction Stop
}
catch [System.IO.FileNotFoundException] {
    Write-Error 'Configuration file not found.'
}
catch {
    Write-Error "Unexpected error: $($_.Exception.Message)"
    throw
}
finally {
    Write-Verbose 'Configuration attempt completed.'
}
```

## Error Preferences

```powershell
$ErrorActionPreference = 'Stop'
Get-Item './missing.txt' -ErrorAction SilentlyContinue -ErrorVariable itemError
$Error[0]
```

## Throw Errors

```powershell
if (-not $configuration) {
    throw [System.InvalidOperationException]::new('Configuration is required.')
}
```

## Native Commands

```powershell
& git status
if ($LASTEXITCODE -ne 0) {
    throw "git failed with exit code $LASTEXITCODE"
}
```

PowerShell distinguishes non-terminating, statement-terminating and script-terminating errors. Use `-ErrorAction Stop` when a non-terminating cmdlet error must be handled by `catch`.
