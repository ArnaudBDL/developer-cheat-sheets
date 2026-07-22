# Terraform : Import

## Import Block

```hcl
import {
  to = aws_s3_bucket.assets
  id = "existing-assets-bucket"
}
```

## Resource Configuration

```hcl
resource "aws_s3_bucket" "assets" {
  bucket = "existing-assets-bucket"
}
```

## CLI Import

```bash
terraform import aws_s3_bucket.assets existing-assets-bucket
terraform plan
```

## Workflow

```text
Identify the exact provider import identifier.
Write the destination resource or module configuration.
Back up state.
Import the remote object.
Run plan and reconcile configuration until unintended changes disappear.
Review ownership before applying.
```

Import associates an existing remote object with a Terraform address. It does not automatically guarantee that the written configuration matches the object's complete remote settings.
