# AWS : Troubleshooting

## Identity and Configuration

```bash
aws --version
aws configure list
aws configure list-profiles
aws sts get-caller-identity
aws ec2 describe-regions --output table
AWS_PROFILE=production AWS_REGION=eu-west-3 aws sts get-caller-identity
```

## Diagnostics

```bash
aws COMMAND --debug
aws cloudtrail lookup-events --max-results 20
aws cloudformation describe-stack-events --stack-name STACK_NAME
aws logs tail LOG_GROUP_NAME --since 1h
aws ec2 describe-instance-status --include-all-instances
```

```text
AccessDenied
  Verify caller identity, explicit denies, policy conditions, resource policy and organization controls.

Resource not found
  Verify account, profile, region, resource identifier and service endpoint.

ExpiredToken or invalid credentials
  Refresh the active session and inspect credential source precedence.

Throttling
  Reduce request rate and use supported retry and backoff behavior.

Network timeout
  Inspect routes, security groups, network ACLs, DNS, endpoints and service reachability.

CloudFormation rollback
  Inspect stack events from the first failing resource and validate dependencies and permissions.
```
