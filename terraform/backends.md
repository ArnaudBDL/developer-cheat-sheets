# Terraform : Backends

## Purpose

```text
A backend defines where Terraform stores state and can define how operations
coordinate access to that state.
```

## Backend Block

```hcl
terraform {
  backend "s3" {
    bucket = "example-terraform-state"
    key    = "production/application.tfstate"
    region = "eu-west-3"
  }
}
```

## Initialization

```bash
terraform init
terraform init -reconfigure
terraform init -migrate-state
terraform init -backend-config=production.backend.hcl
```

- Only one backend block can be configured.
- Backend blocks cannot reference variables, locals or resource attributes.
- Do not hardcode backend credentials.
- Confirm whether the selected backend supports locking and required collaboration features.
- Enable access control, encryption, recovery and versioning appropriate to the backend.
- Review state migration prompts carefully.
