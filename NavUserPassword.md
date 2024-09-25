# How to set up NavUserPassword authentication

### 1. Create a user account.
```PowerShell
New-NAVServerUser -ServerInstance <ServerInstanceName> -UserName <UserName> -Password (Read-Host "Enter Password" -AsSecureString)
```

### 2. Set permissions.
```PowerShell
New-NAVServerUserPermissionSet -PermissionSetId SUPER -ServerInstance  -UserName <UserName>
```
### 3. Set the NAVServerConfiguration.
```PowerShell
Set-NAVServerConfiguration -ServerInstance <ServerInstanceName>  -KeyName ClientServicesCredentialType -KeyValue NavUserPassword
```

### 4. Restart the server instance.
```PowerShell
Restart-NAVServerInstance -ServerInstance <ServerInstanceName>
```

### 5. Configure Web Server components.
```PowerShell
Set-NAVWebServerInstanceConfiguration -WebServerInstance <ServerInstanceName> -KeyName ClientServicesCredentialType -KeyValue NavUserPassword
```

### 6. Restart IIS service.
```PowerShell
iisreset /restart
```