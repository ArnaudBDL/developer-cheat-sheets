# Terraform : Variables

## Declaration

```hcl
variable "environment" {
  description = "Deployment environment"
  type        = string

  validation {
    condition     = contains(["development", "staging", "production"], var.environment)
    error_message = "Environment must be development, staging or production."
  }
}
```

## Complex Type

```hcl
variable "service" {
  type = object({
    name     = string
    replicas = number
    tags     = map(string)
  })
}
```

## Sensitive Variable

```hcl
variable "api_token" {
  type      = string
  sensitive = true
}
```

## Supplying Values

```bash
terraform plan -var='environment=staging'
terraform plan -var-file='staging.tfvars'
export TF_VAR_environment=staging
```

Sensitive values can still exist in state. Keep variable files with secrets out of source control and protect the state backend.
