# PowerShell : Cmdlets

## Verb-Noun Convention

```powershell
Get-Process
Stop-Process
Get-Service
Start-Service
Get-ChildItem
Set-Location
```

## Discover Commands

```powershell
Get-Command
Get-Command -Verb Get
Get-Command -Noun Process
Get-Command -Module Microsoft.PowerShell.Management
Get-Verb
```

## Inspect Syntax and Parameters

```powershell
Get-Command Get-ChildItem -Syntax
Get-Help Get-ChildItem
Get-Help Get-ChildItem -Examples
Get-Help Get-ChildItem -Parameter Path
```

## Common Parameters

```text
-Verbose
-Debug
-ErrorAction
-ErrorVariable
-WarningAction
-InformationAction
-OutVariable
-PipelineVariable
-WhatIf
-Confirm
```
