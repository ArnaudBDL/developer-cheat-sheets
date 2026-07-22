# Azure : Virtual Networks

```bash
az network vnet create   --resource-group application-rg   --name application-vnet   --address-prefix 10.0.0.0/16   --subnet-name application-subnet   --subnet-prefix 10.0.1.0/24

az network vnet list --resource-group application-rg --output table
az network vnet subnet list --resource-group application-rg   --vnet-name application-vnet --output table
```

```bash
az network nsg create --resource-group application-rg --name application-nsg
az network nsg rule create --resource-group application-rg   --nsg-name application-nsg --name AllowHttps   --priority 100 --direction Inbound --access Allow   --protocol Tcp --destination-port-ranges 443
```

Use Network Watcher, NSG flow information and packet capture for network diagnostics.
