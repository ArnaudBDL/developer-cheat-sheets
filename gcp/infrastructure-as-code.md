# GCP : Infrastructure as Code

## Terraform Provider

```hcl
terraform {
  required_providers {
    google = {
      source  = "hashicorp/google"
      version = "~> 7.0"
    }
  }
}

provider "google" {
  project = var.project_id
  region  = var.region
}

resource "google_storage_bucket" "assets" {
  name                        = var.bucket_name
  location                    = var.region
  uniform_bucket_level_access = true
  public_access_prevention    = "enforced"
}
```

## Workflow

```bash
gcloud auth application-default login
terraform init
terraform fmt -check
terraform validate
terraform plan -out=tfplan
terraform apply tfplan
terraform show
```

## Rules

- Store state in an approved remote backend with access controls and locking.
- Review plans before apply.
- Pin provider versions and commit the lock file.
- Keep secrets out of configuration, plans and logs.
- Import existing resources before managing them.
- Avoid mixing authoritative and additive IAM resources for the same role scope.
