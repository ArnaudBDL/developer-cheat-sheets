# Azure : CLI

```bash
az version
az login
az account list --output table
az account set --subscription SUBSCRIPTION_ID
az configure --defaults location=westeurope group=application-rg
az find "az vm create"
az logout
```

```bash
az resource list --output table
az resource show --ids RESOURCE_ID
az resource delete --ids RESOURCE_ID
```

Use `--query` for JMESPath filtering and `--output table|json|tsv|yaml` for output formatting.
