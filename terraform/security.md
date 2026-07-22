# Terraform : Security

## Core Controls

```text
Least-privilege provider identities
Short-lived credentials
Protected remote state
Encrypted backend transport and storage
State locking where supported
Reviewed plans
Pinned Terraform, provider and module versions
Policy checks
Audit logs
Separate production access
```

## Secret Handling

```text
Do not hardcode credentials in HCL.
Do not commit secret tfvars files.
Use approved workload identity or secret injection.
Assume sensitive values may be persisted in state.
Restrict access to plans because they can expose sensitive values.
```

## Supply Chain

```bash
terraform providers lock
terraform init
terraform validate
```

- Review external providers and modules before adoption.
- Commit and verify `.terraform.lock.hcl`.
- Require human approval for destructive production plans.
- Apply policy and security scanning in CI.
- Preserve recoverable state history.
- Avoid local-exec and remote-exec provisioners unless clearly justified and controlled.
