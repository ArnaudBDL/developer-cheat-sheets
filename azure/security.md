# Azure : Security

```bash
az role assignment list --all --output table
az lock create --name protect-production --lock-type CanNotDelete   --resource-group application-rg
az security assessment list --output table
az keyvault create --resource-group application-rg --name UNIQUE_KEYVAULT_NAME   --location westeurope --enable-rbac-authorization true
```

```bash
az keyvault secret set --vault-name UNIQUE_KEYVAULT_NAME   --name ApplicationSecret --value 'SECRET_VALUE'
```

Apply least privilege, managed identities, private endpoints, encryption, diagnostic logging, policy enforcement, secret rotation and update management. Do not place credentials in scripts, templates or repositories.
