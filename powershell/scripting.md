# PowerShell : Scripting

## Script Template

```powershell
#Requires -Version 7.4

[CmdletBinding(SupportsShouldProcess)]
param(
    [Parameter(Mandatory)]
    [ValidateNotNullOrEmpty()]
    [string] $ConfigurationPath,

    [ValidateSet('Development', 'Test', 'Production')]
    [string] $Environment = 'Development'
)

Set-StrictMode -Version Latest
$ErrorActionPreference = 'Stop'

try {
    $resolvedPath = Resolve-Path -LiteralPath $ConfigurationPath
    $configuration = Get-Content -LiteralPath $resolvedPath -Raw | ConvertFrom-Json

    if ($PSCmdlet.ShouldProcess($Environment, 'Apply configuration')) {
        [PSCustomObject]@{
            Environment = $Environment
            Path        = $resolvedPath.Path
            Applied     = $true
        }
    }
}
catch {
    Write-Error "Script failed: $($_.Exception.Message)"
    exit 1
}
```

## Run Scripts

```powershell
./Configure-Application.ps1 -ConfigurationPath './config.json' -Environment Production
pwsh -File './Configure-Application.ps1' -ConfigurationPath './config.json'
```

## Script Practices

- Use `#Requires` for version and module prerequisites.
- Use parameter validation and meaningful defaults.
- Use `Set-StrictMode` in controlled scripts and test its impact.
- Prefer `-LiteralPath` when paths may contain wildcard characters.
- Use `SupportsShouldProcess` for destructive operations.
- Return structured objects rather than formatted strings.
- Check native command exit codes.
- Avoid embedding secrets in scripts, arguments or logs.
- Add Pester tests and static analysis for reusable automation.
