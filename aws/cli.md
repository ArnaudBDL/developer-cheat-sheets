# AWS : CLI

## Configuration

```bash
aws --version
aws configure
aws configure --profile production
aws configure list
aws configure list-profiles
aws sts get-caller-identity
```

## Usage

```bash
aws help
aws ec2 help
aws ec2 describe-instances help
aws ec2 describe-regions --output table
aws s3 ls --profile production --region eu-west-3
```

Use `--query` for JMESPath filtering and `--output json|yaml|text|table` for output formatting. Prefer short-lived credentials, IAM roles or supported federated authentication over static access keys.
