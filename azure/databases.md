# Azure : Databases

```bash
az postgres flexible-server create   --resource-group application-rg   --name UNIQUE_POSTGRES_NAME   --location westeurope   --admin-user dbadmin   --admin-password 'STRONG_PASSWORD'

az postgres flexible-server db create --resource-group application-rg   --server-name UNIQUE_POSTGRES_NAME --database-name application
```

```bash
az sql server create --resource-group application-rg   --name UNIQUE_SQL_SERVER --location westeurope   --admin-user sqladmin --admin-password 'STRONG_PASSWORD'
az sql db create --resource-group application-rg   --server UNIQUE_SQL_SERVER --name application --service-objective S0
```

Use private networking, firewall restrictions, Microsoft Entra authentication where supported, backups and monitoring appropriate to the selected database service.
