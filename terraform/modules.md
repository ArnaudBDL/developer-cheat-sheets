# Terraform : Modules

## Local Module

```hcl
module "network" {
  source = "./modules/network"

  name       = "core"
  cidr_block = "10.20.0.0/16"
}
```

## Registry Module

```hcl
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "~> 6.0"

  name = "application"
  cidr = "10.30.0.0/16"
}
```

## Structure

```text
modules/network/
├── main.tf
├── variables.tf
├── outputs.tf
└── README.md
```

## Commands

```bash
terraform init
terraform get -update
terraform providers
```

Modules are reusable Terraform configurations. Pin external module versions, keep interfaces small, validate inputs, document outputs, and test upgrades before promotion.
