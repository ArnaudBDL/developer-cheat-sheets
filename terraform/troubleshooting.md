# Terraform : Troubleshooting

## Baseline

```bash
terraform version
terraform fmt -check -recursive
terraform init
terraform validate
terraform providers
terraform plan
```

## Initialization Failures

```bash
terraform init -reconfigure
terraform init -upgrade
rm -rf .terraform
terraform init
```

Remove `.terraform` only when local initialization metadata and downloaded plugins can safely be rebuilt. Do not delete state.

## State and Drift

```bash
terraform state list
terraform state show ADDRESS
terraform plan -refresh-only
terraform apply -refresh-only
```

## Debug Logs

```bash
TF_LOG=DEBUG terraform plan
TF_LOG=TRACE TF_LOG_PATH=terraform.log terraform plan
```

Debug logs may contain sensitive values. Protect and remove them after analysis.

## Checks

```text
Authentication and provider permissions
Provider and Terraform version constraints
Backend connectivity and lock ownership
Required variables
Resource addresses after refactoring
Remote object drift
Quota and API errors
Module source and checksum availability
```
