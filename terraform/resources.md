# Terraform : Resources

## Resource Block

```hcl
resource "aws_s3_bucket" "assets" {
  bucket = "example-assets-prod"

  tags = {
    Environment = "production"
    ManagedBy   = "terraform"
  }
}
```

## References

```hcl
resource "aws_s3_bucket_versioning" "assets" {
  bucket = aws_s3_bucket.assets.id

  versioning_configuration {
    status = "Enabled"
  }
}
```

## Meta-Arguments

```text
count
each.key and each.value with for_each
depends_on
provider
lifecycle
```

## Lifecycle Example

```hcl
lifecycle {
  prevent_destroy = true
}
```

Use stable `for_each` keys, prefer references to manual dependencies, and review replacement actions carefully because some argument changes require recreation.
