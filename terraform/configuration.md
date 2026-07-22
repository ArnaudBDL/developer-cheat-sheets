# Terraform : Configuration

## Terraform Block

```hcl
terraform {
  required_version = ">= 1.10, < 2.0"

  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}
```

## Common Files

```text
terraform.tf       Terraform and provider requirements
providers.tf       Provider configuration
variables.tf       Input variables
main.tf            Resources and data sources
outputs.tf         Output values
locals.tf          Local values
versions.tf        Alternative version requirements file
```

## Commands

```bash
terraform fmt -recursive
terraform validate
terraform providers
terraform graph
terraform console
```

- Keep configuration declarative.
- Use consistent naming and formatting.
- Separate environments when credentials, access controls or lifecycle differ.
- Avoid hardcoded credentials and environment-specific secrets.
- Review the execution plan before applying changes.
