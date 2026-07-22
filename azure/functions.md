# Azure : Functions

```bash
func --version
func init application-functions --worker-runtime node --language typescript
cd application-functions
func new --template "HTTP trigger" --name Health
func start
```

```bash
az functionapp create   --resource-group application-rg   --consumption-plan-location westeurope   --runtime node   --functions-version 4   --name UNIQUE_FUNCTION_NAME   --storage-account UNIQUE_STORAGE_NAME

func azure functionapp publish UNIQUE_FUNCTION_NAME
az functionapp log tail --resource-group application-rg --name UNIQUE_FUNCTION_NAME
```

Store secrets outside source code and use managed identity when the function accesses Azure resources.
