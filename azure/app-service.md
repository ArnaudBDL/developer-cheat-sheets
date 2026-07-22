# Azure : App Service

```bash
az appservice plan create   --resource-group application-rg   --name application-plan   --sku B1   --is-linux

az webapp create   --resource-group application-rg   --plan application-plan   --name UNIQUE_WEBAPP_NAME   --runtime "NODE:22-lts"

az webapp config appsettings set --resource-group application-rg   --name UNIQUE_WEBAPP_NAME --settings NODE_ENV=production
az webapp log tail --resource-group application-rg --name UNIQUE_WEBAPP_NAME
```

```bash
az webapp deployment source config-zip --resource-group application-rg   --name UNIQUE_WEBAPP_NAME --src application.zip
az webapp restart --resource-group application-rg --name UNIQUE_WEBAPP_NAME
```
