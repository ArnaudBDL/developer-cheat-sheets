# AWS : CloudFront

## Distributions

```bash
aws cloudfront list-distributions   --query 'DistributionList.Items[].{Id:Id,Domain:DomainName,Enabled:Enabled}'   --output table

aws cloudfront get-distribution --id DISTRIBUTION_ID
aws cloudfront get-distribution-config --id DISTRIBUTION_ID
```

## Invalidation

```bash
aws cloudfront create-invalidation   --distribution-id DISTRIBUTION_ID   --paths '/index.html' '/assets/*'

aws cloudfront list-invalidations --distribution-id DISTRIBUTION_ID
```

Use origin access controls for private S3 origins, HTTPS viewer policies, appropriate cache policies and restricted alternate domain names.
