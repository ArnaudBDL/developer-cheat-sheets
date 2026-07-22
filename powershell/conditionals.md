# PowerShell : Conditionals

## if, elseif and else

```powershell
if ($status -eq 'ready') {
    Write-Output 'Ready'
}
elseif ($status -eq 'error') {
    Write-Warning 'Error'
}
else {
    Write-Output 'Pending'
}
```

## switch

```powershell
switch ($status) {
    'ready' { Write-Output 'Ready'; break }
    'error' { Write-Error 'Error'; break }
    default { Write-Output 'Pending' }
}
```

## Regex and Wildcard Switch

```powershell
switch -Regex ($message) {
    '^ERROR:' { 'Error message' }
    '^WARN:'  { 'Warning message' }
}

switch -Wildcard ($fileName) {
    '*.json' { 'JSON file' }
    '*.csv'  { 'CSV file' }
}
```

## Ternary Operator

```powershell
$label = $enabled ? 'Enabled' : 'Disabled'
```
