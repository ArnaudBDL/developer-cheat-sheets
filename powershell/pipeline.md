# PowerShell : Pipeline

## Object Pipeline

```powershell
Get-Process |
    Where-Object CPU -gt 10 |
    Sort-Object CPU -Descending |
    Select-Object -First 10 Name, Id, CPU
```

PowerShell sends objects through the pipeline, preserving properties and methods until output is formatted or converted to text.

## Common Pipeline Cmdlets

```powershell
Where-Object
ForEach-Object
Select-Object
Sort-Object
Group-Object
Measure-Object
Tee-Object
Export-Csv
ConvertTo-Json
```

## Current Object

```powershell
Get-ChildItem -File |
    Where-Object { $_.Length -gt 1MB } |
    ForEach-Object { $_.FullName }
```

## Pipeline Input in a Function

```powershell
function Get-UpperName {
    [CmdletBinding()]
    param(
        [Parameter(ValueFromPipeline)]
        [string] $Name
    )

    process {
        $Name.ToUpperInvariant()
    }
}
```
