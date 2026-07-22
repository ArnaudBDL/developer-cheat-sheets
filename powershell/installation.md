# PowerShell : Installation

## Verify the Installation

```powershell
$PSVersionTable
$PSVersionTable.PSVersion
Get-Host
```

## Windows

```powershell
winget search Microsoft.PowerShell
winget install --id Microsoft.PowerShell --source winget
pwsh
```

## macOS

```bash
brew install --cask powershell
pwsh
```

## Linux

Use the package repository and installation procedure documented for the target distribution, then start PowerShell with:

```bash
pwsh
```

## Update Help

```powershell
Update-Help
Get-Help Get-Process -Full
Get-Help about_Pipelines
```
