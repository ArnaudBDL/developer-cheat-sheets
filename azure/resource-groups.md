# Azure : Resource Groups

```bash
az group create --name application-rg --location westeurope
az group list --output table
az group show --name application-rg
az group update --name application-rg --set tags.environment=production
az group export --name application-rg > exported-template.json
az group delete --name application-rg --yes --no-wait
```

A resource group contains related Azure resources. Group resources that share a lifecycle, ownership boundary and deployment scope.
