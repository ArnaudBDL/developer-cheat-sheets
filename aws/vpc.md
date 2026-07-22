# AWS : VPC

## Network

```bash
aws ec2 create-vpc --cidr-block 10.0.0.0/16   --tag-specifications 'ResourceType=vpc,Tags=[{Key=Name,Value=application-vpc}]'

aws ec2 create-subnet --vpc-id VPC_ID   --cidr-block 10.0.1.0/24 --availability-zone eu-west-3a

aws ec2 create-internet-gateway
aws ec2 attach-internet-gateway --vpc-id VPC_ID --internet-gateway-id IGW_ID
aws ec2 create-route-table --vpc-id VPC_ID
aws ec2 create-route --route-table-id ROUTE_TABLE_ID   --destination-cidr-block 0.0.0.0/0 --gateway-id IGW_ID
```

## Security Groups

```bash
aws ec2 create-security-group   --group-name application-web   --description 'Application HTTPS access'   --vpc-id VPC_ID

aws ec2 authorize-security-group-ingress   --group-id SECURITY_GROUP_ID   --protocol tcp --port 443 --cidr TRUSTED_CIDR

aws ec2 describe-route-tables --filters Name=vpc-id,Values=VPC_ID
aws ec2 describe-network-acls --filters Name=vpc-id,Values=VPC_ID
```
