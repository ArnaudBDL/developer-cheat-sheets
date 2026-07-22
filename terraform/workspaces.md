# Terraform : Workspaces

## Commands

```bash
terraform workspace list
terraform workspace show
terraform workspace new development
terraform workspace select development
terraform workspace delete development
```

## Current Workspace

```hcl
locals {
  resource_prefix = "application-${terraform.workspace}"
}
```

## Behavior

```text
The default workspace always exists.
Each CLI workspace has separate state for the same configuration.
Backend support for multiple workspaces varies.
Terraform CLI workspaces differ from HCP Terraform workspaces.
```

Workspaces are not suitable for system decomposition or deployments requiring separate credentials and access controls. Use separate configurations and backends when stronger isolation is required.
