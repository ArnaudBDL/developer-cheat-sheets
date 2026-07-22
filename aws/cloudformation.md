# AWS : CloudFormation

## Template

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Private S3 bucket
Resources:
  AssetsBucket:
    Type: AWS::S3::Bucket
    Properties:
      PublicAccessBlockConfiguration:
        BlockPublicAcls: true
        IgnorePublicAcls: true
        BlockPublicPolicy: true
        RestrictPublicBuckets: true
      BucketEncryption:
        ServerSideEncryptionConfiguration:
          - ServerSideEncryptionByDefault:
              SSEAlgorithm: AES256
```

## Validate and Deploy

```bash
aws cloudformation validate-template --template-body file://template.yaml
aws cloudformation deploy   --template-file template.yaml   --stack-name application-stack   --capabilities CAPABILITY_NAMED_IAM

aws cloudformation describe-stacks --stack-name application-stack
aws cloudformation describe-stack-events --stack-name application-stack
aws cloudformation delete-stack --stack-name application-stack
```

Use change sets before sensitive updates and keep environment-specific values in parameters.
