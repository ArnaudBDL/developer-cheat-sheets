# AWS : Security

## Account and Audit

```bash
aws sts get-caller-identity
aws iam get-account-summary
aws accessanalyzer list-analyzers
aws guardduty list-detectors
aws securityhub describe-hub
aws cloudtrail describe-trails
aws configservice describe-configuration-recorders
```

## Encryption and Secrets

```bash
aws kms list-keys
aws kms list-aliases
aws secretsmanager list-secrets
aws secretsmanager get-secret-value --secret-id application/database
```

Use multi-factor authentication, least privilege, workload roles, centralized logs, encryption, secrets rotation, network restrictions, backups and continuous review of public exposure. Do not store access keys in repositories or application images.
