# GCP : Compute Engine

## Instances

```bash
gcloud compute instances create application-vm   --zone=europe-west1-b   --machine-type=e2-medium   --image-family=debian-12   --image-project=debian-cloud   --service-account=application-runtime@PROJECT_ID.iam.gserviceaccount.com   --scopes=cloud-platform

gcloud compute instances list
gcloud compute instances describe application-vm --zone=europe-west1-b
gcloud compute ssh application-vm --zone=europe-west1-b
gcloud compute instances stop application-vm --zone=europe-west1-b
gcloud compute instances start application-vm --zone=europe-west1-b
gcloud compute instances delete application-vm --zone=europe-west1-b
```

## Disks and Snapshots

```bash
gcloud compute disks list
gcloud compute snapshots create application-disk-snapshot   --source-disk=application-vm   --source-disk-zone=europe-west1-b
gcloud compute snapshots list
```

Use OS Login, least-privileged service accounts, restricted firewall rules and Shielded VM features where appropriate.
