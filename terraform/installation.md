# Terraform : Installation

## Verify

```bash
terraform version
terraform -help
```

## macOS

```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
brew upgrade hashicorp/tap/terraform
```

## Shell Completion

```bash
terraform -install-autocomplete
```

## Project Initialization

```bash
mkdir infrastructure
cd infrastructure
terraform init
terraform fmt -recursive
terraform validate
```

- Install Terraform from an approved package or official distribution.
- Pin the Terraform version used by local development and CI.
- Commit `.terraform.lock.hcl`.
- Do not commit `.terraform/`, state files or local variable files containing secrets.
- Verify provider checksums during `terraform init`.
