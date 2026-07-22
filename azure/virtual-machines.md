# Azure : Virtual Machines

```bash
az vm create   --resource-group application-rg   --name application-vm   --image Ubuntu2204   --admin-username azureuser   --generate-ssh-keys

az vm list --resource-group application-rg --output table
az vm get-instance-view --resource-group application-rg --name application-vm
az vm start --resource-group application-rg --name application-vm
az vm stop --resource-group application-rg --name application-vm
az vm deallocate --resource-group application-rg --name application-vm
az vm delete --resource-group application-rg --name application-vm --yes
```

```bash
az vm open-port --resource-group application-rg --name application-vm --port 22
az vm run-command invoke --resource-group application-rg --name application-vm   --command-id RunShellScript --scripts 'uname -a'
```
