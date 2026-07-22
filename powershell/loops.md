# PowerShell : Loops

## foreach

```powershell
foreach ($item in $items) {
    Write-Output $item.Name
}
```

## ForEach-Object

```powershell
Get-Process | ForEach-Object {
    [PSCustomObject]@{
        Name = $_.Name
        Id   = $_.Id
    }
}
```

## for

```powershell
for ($index = 0; $index -lt $items.Count; $index++) {
    Write-Output $items[$index]
}
```

## while and do

```powershell
while ($attempt -lt 3) {
    $attempt++
}

do {
    $attempt++
} while ($attempt -lt 3)
```

## Loop Control

```powershell
break
continue
return
```
