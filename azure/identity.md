# Azure : Identity

```bash
az account show
az ad signed-in-user show
az identity create --resource-group application-rg --name application-identity
az identity show --resource-group application-rg --name application-identity
```

```bash
SCOPE=$(az group show --name application-rg --query id --output tsv)
az role assignment create   --assignee-object-id PRINCIPAL_OBJECT_ID   --assignee-principal-type ServicePrincipal   --role Reader   --scope "$SCOPE"
az role assignment list --scope "$SCOPE" --output table
```

Prefer managed identities for Azure-hosted workloads and assign the narrowest role at the smallest practical scope.
