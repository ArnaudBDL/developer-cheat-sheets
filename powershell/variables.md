# PowerShell : Variables

## Declaration and Assignment

```powershell
$name = 'PowerShell'
$count = 42
$enabled = $true
$nothing = $null
[string] $environment = 'production'
[int] $retryCount = 3
```

## Interpolation

```powershell
"Hello $name"
"Process count: $((Get-Process).Count)"
'Literal $name'
```

## Scopes

```powershell
$global:ApplicationName = 'Application'
$script:Configuration = @{}
$local:CurrentValue = 42
$private:InternalValue = 'hidden'
```

## Environment Variables

```powershell
$env:PATH
$env:APPLICATION_ENV = 'production'
Get-ChildItem Env:
Remove-Item Env:APPLICATION_ENV
```

## Useful Automatic Variables

```powershell
$PSVersionTable
$PSScriptRoot
$PSCommandPath
$LASTEXITCODE
$Error
$_
$input
$args
```
