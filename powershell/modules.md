# PowerShell : Modules

## Discover and Import

```powershell
Get-Module
Get-Module -ListAvailable
Import-Module Microsoft.PowerShell.Management
Remove-Module ModuleName
Get-Command -Module ModuleName
```

## Install Modules

```powershell
Find-Module Pester
Install-Module Pester -Scope CurrentUser
Update-Module Pester
Uninstall-Module Pester
```

## Module Structure

```text
ApplicationModule/
├── ApplicationModule.psd1
├── ApplicationModule.psm1
├── Public/
└── Private/
```

## Create a Manifest

```powershell
New-ModuleManifest     -Path './ApplicationModule/ApplicationModule.psd1'     -RootModule 'ApplicationModule.psm1'     -ModuleVersion '1.0.0'     -FunctionsToExport @('Get-ApplicationStatus')

Test-ModuleManifest './ApplicationModule/ApplicationModule.psd1'
```

## Export Members

```powershell
Export-ModuleMember -Function Get-ApplicationStatus
```
