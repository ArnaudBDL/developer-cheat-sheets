# AWS : EC2

## Instances

```bash
aws ec2 describe-instances   --query 'Reservations[].Instances[].{Id:InstanceId,State:State.Name,Type:InstanceType}'   --output table

aws ec2 run-instances   --image-id AMI_ID   --instance-type t3.micro   --subnet-id SUBNET_ID   --security-group-ids SECURITY_GROUP_ID   --iam-instance-profile Name=INSTANCE_PROFILE   --count 1

aws ec2 start-instances --instance-ids INSTANCE_ID
aws ec2 stop-instances --instance-ids INSTANCE_ID
aws ec2 reboot-instances --instance-ids INSTANCE_ID
aws ec2 terminate-instances --instance-ids INSTANCE_ID
```

## Images and Volumes

```bash
aws ec2 describe-images --owners self
aws ec2 describe-volumes --filters Name=attachment.instance-id,Values=INSTANCE_ID
aws ec2 create-snapshot --volume-id VOLUME_ID --description 'Application backup'
```
