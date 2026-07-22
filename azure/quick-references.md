# Azure : Quick References

## Session

```bash
az login
az account list -o table
az account set --subscription SUBSCRIPTION_ID
az account show -o table
```

## Resources

```bash
az group list -o table
az resource list -g RESOURCE_GROUP -o table
az group create -n RESOURCE_GROUP -l LOCATION
az group delete -n RESOURCE_GROUP
```

## Web apps and logs

```bash
az webapp list -o table
az webapp restart -g RESOURCE_GROUP -n APP_NAME
az webapp log tail -g RESOURCE_GROUP -n APP_NAME
```
