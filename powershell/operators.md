# PowerShell : Operators

## Comparison

```powershell
$value -eq 42
$value -ne 0
$value -gt 10
$value -ge 10
$value -lt 100
$value -le 100
$name -like 'Power*'
$name -match '^Power'
```

## Logical

```powershell
$enabled -and $ready
$failed -or $expired
-not $completed
!$completed
```

## Collection

```powershell
'admin' -in $roles
$roles -contains 'admin'
$values -join ', '
'a,b,c' -split ','
1..10
```

## Type and Null

```powershell
$value -is [string]
$value -isnot [int]
$result = $value ?? 'default'
$value ??= 'default'
```

## Formatting

```powershell
'User: {0}, Status: {1}' -f $name, $status
```
