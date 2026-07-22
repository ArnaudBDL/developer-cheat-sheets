# PowerShell : Remoting

## Interactive and One-to-One

```powershell
Test-WSMan -ComputerName server01
Enter-PSSession -ComputerName server01
Exit-PSSession
```

## Invoke Commands

```powershell
Invoke-Command -ComputerName server01, server02 -ScriptBlock {
    Get-Service
}

Invoke-Command -ComputerName server01 -FilePath './Get-Status.ps1'
```

## Persistent Sessions

```powershell
$session = New-PSSession -ComputerName server01
Invoke-Command -Session $session -ScriptBlock { $env:COMPUTERNAME }
Copy-Item './config.json' -Destination 'C:\Application\config.json' -ToSession $session
Remove-PSSession $session
```

## SSH Transport

```powershell
Enter-PSSession -HostName server.example.com -UserName administrator
Invoke-Command -HostName server.example.com -UserName administrator -ScriptBlock {
    Get-Process
}
```

Use trusted hosts, authenticated users, least privilege, encrypted transports and explicit endpoint configuration. Do not disable security checks merely to make remoting connect.
