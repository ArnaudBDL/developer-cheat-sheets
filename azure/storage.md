# Azure : Storage

```bash
az storage account create   --resource-group application-rg   --name UNIQUE_STORAGE_NAME   --location westeurope   --sku Standard_LRS   --kind StorageV2   --https-only true

az storage account show --resource-group application-rg --name UNIQUE_STORAGE_NAME
```

```bash
az storage container create --account-name UNIQUE_STORAGE_NAME --name assets --auth-mode login
az storage blob upload --account-name UNIQUE_STORAGE_NAME --container-name assets   --name document.txt --file document.txt --auth-mode login
az storage blob list --account-name UNIQUE_STORAGE_NAME --container-name assets   --auth-mode login --output table
```

Disable public access unless it is explicitly required and prefer Microsoft Entra authentication over account keys.
