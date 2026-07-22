# Terraform : Providers

## Requirement

```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "~> 4.0"
    }
  }
}
```

## Configuration

```hcl
provider "azurerm" {
  features {}
}
```

## Aliases

```hcl
provider "aws" {
  region = "eu-west-3"
}

provider "aws" {
  alias  = "secondary"
  region = "eu-west-1"
}
```

## Commands

```bash
terraform init
terraform init -upgrade
terraform providers
terraform providers lock
```

Providers are plugins that expose resources and data sources and perform API calls. Pin compatible versions, commit the lock file, and supply credentials through the provider's supported secure mechanisms rather than HCL literals.
