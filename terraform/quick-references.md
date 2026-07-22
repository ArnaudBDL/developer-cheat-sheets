# Terraform : Quick References

## Workflow

```bash
terraform init
terraform fmt -recursive
terraform validate
terraform plan
terraform apply
terraform destroy
```

## State

```bash
terraform state list
terraform state show RESOURCE
terraform import RESOURCE ID
terraform output
terraform workspace list
```

## Automation

```bash
terraform plan -out=tfplan
terraform apply tfplan
terraform apply -auto-approve
terraform destroy -auto-approve
```
