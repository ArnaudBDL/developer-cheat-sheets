# PowerShell : Files

## Paths and Items

```powershell
Join-Path $PSScriptRoot 'config.json'
Test-Path -LiteralPath './config.json'
Resolve-Path './config.json'
Get-Item './config.json'
Get-ChildItem -Path './logs' -File -Recurse
```

## Read and Write Text

```powershell
Get-Content -LiteralPath './input.txt'
Get-Content -LiteralPath './application.log' -Tail 50 -Wait
Set-Content -LiteralPath './output.txt' -Value 'Content' -Encoding utf8
Add-Content -LiteralPath './output.txt' -Value 'Additional line'
```

## Copy, Move and Remove

```powershell
Copy-Item -LiteralPath './source.txt' -Destination './copy.txt'
Move-Item -LiteralPath './copy.txt' -Destination './archive/copy.txt'
Remove-Item -LiteralPath './archive/copy.txt' -WhatIf
```

## Structured Data

```powershell
$data = Get-Content './config.json' -Raw | ConvertFrom-Json
$data | ConvertTo-Json -Depth 10 | Set-Content './config.json' -Encoding utf8
Import-Csv './users.csv'
$users | Export-Csv './users.csv' -NoTypeInformation -Encoding utf8
```
