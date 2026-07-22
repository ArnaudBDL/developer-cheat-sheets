# AWS : Quick References

## Identity and configuration

```bash
aws configure
aws sts get-caller-identity
aws configure list
aws configure list-profiles
```

## S3

```bash
aws s3 ls
aws s3 ls s3://BUCKET
aws s3 cp FILE s3://BUCKET/
aws s3 sync DIRECTORY s3://BUCKET/PREFIX
aws s3 rm s3://BUCKET/KEY
```

## EC2 and logs

```bash
aws ec2 describe-instances
aws ec2 start-instances --instance-ids INSTANCE_ID
aws ec2 stop-instances --instance-ids INSTANCE_ID
aws logs tail LOG_GROUP --follow
```
