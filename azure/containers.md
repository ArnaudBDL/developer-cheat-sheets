# Azure : Containers

```bash
az acr create --resource-group application-rg --name UNIQUE_ACR_NAME --sku Basic
az acr login --name UNIQUE_ACR_NAME
az acr build --registry UNIQUE_ACR_NAME --image application:v1 .
az acr repository list --name UNIQUE_ACR_NAME --output table
```

```bash
az container create   --resource-group application-rg   --name application-container   --image UNIQUE_ACR_NAME.azurecr.io/application:v1   --cpu 1 --memory 1.5   --ports 8080   --ip-address Public

az container logs --resource-group application-rg --name application-container
```

For orchestrated workloads, inspect Azure Kubernetes Service and Azure Container Apps according to scaling and operational requirements.
