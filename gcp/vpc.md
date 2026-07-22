# GCP : VPC

## Networks and Subnets

```bash
gcloud compute networks create application-vpc   --subnet-mode=custom

gcloud compute networks subnets create application-subnet   --network=application-vpc   --region=europe-west1   --range=10.10.0.0/24   --enable-private-ip-google-access

gcloud compute networks list
gcloud compute networks subnets list --network=application-vpc
```

## Firewall Rules

```bash
gcloud compute firewall-rules create allow-https   --network=application-vpc   --direction=INGRESS   --action=ALLOW   --rules=tcp:443   --source-ranges=TRUSTED_CIDR   --target-tags=https-server

gcloud compute firewall-rules list --filter='network:application-vpc'
```

## Diagnostics

```bash
gcloud compute routes list --filter='network:application-vpc'
gcloud compute networks peerings list --network=application-vpc
gcloud network-management connectivity-tests list
```

Prefer private connectivity, narrowly scoped firewall rules and controlled egress for sensitive workloads.
