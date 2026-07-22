# Azure : Infrastructure as Code

```bicep
param location string = resourceGroup().location
param storageName string

resource storage 'Microsoft.Storage/storageAccounts@2023-05-01' = {
  name: storageName
  location: location
  sku: { name: 'Standard_LRS' }
  kind: 'StorageV2'
  properties: {
    supportsHttpsTrafficOnly: true
    allowBlobPublicAccess: false
    minimumTlsVersion: 'TLS1_2'
  }
}

output storageId string = storage.id
```

```bash
az bicep version
az bicep build --file main.bicep
az deployment group what-if --resource-group application-rg   --template-file main.bicep --parameters storageName=UNIQUE_STORAGE_NAME
az deployment group create --resource-group application-rg   --template-file main.bicep --parameters storageName=UNIQUE_STORAGE_NAME
```

Keep environment values in parameter files and reusable resource patterns in Bicep modules.
