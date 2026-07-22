# PowerShell : Quick References

## Discovery

```powershell
Get-Command
Get-Help Get-Process -Full
Get-Member
Get-Alias
```

## Pipeline

```powershell
Get-Process |
  Where-Object CPU -gt 10 |
  Sort-Object CPU -Descending |
  Select-Object -First 10 Name, CPU
```

## Files and services

```powershell
Get-ChildItem -Recurse -File
Get-Content .\file.txt
Set-Content .\file.txt "value"
Get-Service
Restart-Service -Name ServiceName
```

## Error handling

```powershell
try {
    Invoke-RestMethod -Uri $Uri -ErrorAction Stop
} catch {
    Write-Error $_.Exception.Message
    exit 1
}
```
