# AWS : IAM

## Identity

```bash
aws sts get-caller-identity
aws iam list-users
aws iam list-roles
aws iam list-policies --scope Local
aws iam get-account-summary
```

## Roles and Policies

```bash
aws iam create-role   --role-name ApplicationRole   --assume-role-policy-document file://trust-policy.json

aws iam attach-role-policy   --role-name ApplicationRole   --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess

aws iam list-attached-role-policies --role-name ApplicationRole
aws iam simulate-principal-policy   --policy-source-arn ROLE_ARN   --action-names s3:GetObject
```

Apply least privilege, use roles for workloads, require multi-factor authentication where appropriate and review unused credentials and permissions.
