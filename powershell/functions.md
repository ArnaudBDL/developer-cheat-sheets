# PowerShell : Functions

## Basic Function

```powershell
function Get-Greeting {
    param(
        [Parameter(Mandatory)]
        [string] $Name
    )

    "Hello $Name"
}
```

## Advanced Function

```powershell
function Remove-ApplicationFile {
    [CmdletBinding(SupportsShouldProcess, ConfirmImpact = 'High')]
    param(
        [Parameter(Mandatory, ValueFromPipeline, ValueFromPipelineByPropertyName)]
        [ValidateNotNullOrEmpty()]
        [string] $Path
    )

    process {
        if ($PSCmdlet.ShouldProcess($Path, 'Remove file')) {
            Remove-Item -LiteralPath $Path -Force
        }
    }
}
```

## Parameter Validation

```powershell
[ValidateSet('Development', 'Test', 'Production')]
[string] $Environment

[ValidateRange(1, 10)]
[int] $RetryCount

[ValidatePattern('^[a-z0-9-]+$')]
[string] $Name
```

Use approved verbs from `Get-Verb` and output objects rather than presentation-only text when the result will continue through a pipeline.
