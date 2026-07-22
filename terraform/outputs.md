# Terraform : Outputs

## Declaration

```hcl
output "bucket_name" {
  description = "Name of the assets bucket"
  value       = aws_s3_bucket.assets.bucket
}
```

## Sensitive Output

```hcl
output "generated_password" {
  value     = random_password.application.result
  sensitive = true
}
```

## Commands

```bash
terraform output
terraform output bucket_name
terraform output -json
terraform output -raw bucket_name
```

Outputs expose selected values to operators, automation and calling modules. Marking an output sensitive reduces normal CLI display but does not remove it from state. Expose only values consumers genuinely require.
