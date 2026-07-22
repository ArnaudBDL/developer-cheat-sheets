# Terraform : State

## Purpose

```text
State maps Terraform resource addresses to remote objects and stores metadata
required to plan and manage infrastructure.
```

## Inspection

```bash
terraform state list
terraform state show aws_s3_bucket.assets
terraform show
terraform show -json
```

## Safe Refactoring

```hcl
moved {
  from = aws_s3_bucket.old_name
  to   = aws_s3_bucket.assets
}
```

## State Commands

```bash
terraform state mv SOURCE DESTINATION
terraform state rm ADDRESS
terraform state pull > terraform.tfstate.backup
```

- Treat state as sensitive because it can contain resource attributes and secrets.
- Prefer remote storage with access controls, encryption, versioning and supported locking.
- Do not edit state JSON manually.
- Back up state before exceptional repair operations.
- Serialize operations that modify the same state.
