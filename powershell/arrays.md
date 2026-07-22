# PowerShell : Arrays

## Create Arrays

```powershell
$numbers = 1, 2, 3
$names = @('Alice', 'Bob')
$empty = @()
$range = 1..10
```

## Access and Slice

```powershell
$names[0]
$names[-1]
$names[0..1]
$names.Count
```

## Filter and Transform

```powershell
$even = $numbers | Where-Object { $_ % 2 -eq 0 }
$doubled = $numbers | ForEach-Object { $_ * 2 }
```

## Strongly Typed Collections

```powershell
[string[]] $servers = 'app-01', 'app-02'
$list = [System.Collections.Generic.List[string]]::new()
$list.Add('value')
```

Repeated `+=` operations recreate arrays. Use a generic list or pipeline collection for larger incremental workloads.
