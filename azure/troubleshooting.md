# Azure : Troubleshooting

```bash
az account show
az account get-access-token
az group show --name application-rg
az resource list --resource-group application-rg --output table
az monitor activity-log list --resource-group application-rg --max-events 50 --output table
az provider show --namespace Microsoft.Compute --query registrationState
az deployment group list --resource-group application-rg --output table
```

```text
AuthorizationFailed
  Verify tenant, subscription, role assignment, scope and token refresh.

ResourceNotFound
  Verify subscription, resource group, resource name, type and region.

DeploymentFailed
  Inspect deployment operations and nested error details.

QuotaExceeded
  Inspect regional quota and requested SKU capacity.

Network failure
  Inspect DNS, routes, NSGs, private endpoints, firewalls and Network Watcher.

CLI command failure
  Run with --debug, inspect extension versions and verify the command reference.
```

```bash
az deployment group show --resource-group application-rg --name DEPLOYMENT_NAME
az deployment operation group list --resource-group application-rg   --name DEPLOYMENT_NAME --output table
az network watcher packet-capture list --location westeurope --output table
```
