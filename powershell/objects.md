# PowerShell : Objects

## Inspect Objects

```powershell
Get-Process | Get-Member
Get-Service | Select-Object Name, Status, StartType
```

## Create Custom Objects

```powershell
$user = [PSCustomObject]@{
    Id      = 42
    Name    = 'Arnaud'
    Active  = $true
    Created = [datetime]::UtcNow
}
```

## Properties and Methods

```powershell
$user.Name
$user.PSObject.Properties
(Get-Process -Id $PID).Kill
```

## Calculated Properties

```powershell
Get-ChildItem -File | Select-Object Name, @{
    Name = 'SizeMB'
    Expression = { [math]::Round($_.Length / 1MB, 2) }
}
```

## Hash Tables

```powershell
$configuration = @{
    Environment = 'Production'
    RetryCount  = 3
}

$configuration['Environment']
$configuration.RetryCount
```
