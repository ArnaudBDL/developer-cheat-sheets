# GCP : Kubernetes Engine

## Clusters

```bash
gcloud container clusters create-auto application-cluster   --region=europe-west1   --release-channel=regular

gcloud container clusters list
gcloud container clusters describe application-cluster --region=europe-west1
gcloud container clusters get-credentials application-cluster --region=europe-west1
kubectl get nodes
kubectl get namespaces
```

## Workloads

```bash
kubectl apply -f deployment.yaml
kubectl get deployments,pods,services
kubectl rollout status deployment/application
kubectl logs deployment/application
kubectl describe pod POD_NAME
```

## Security

```bash
gcloud container clusters update application-cluster   --region=europe-west1   --workload-pool=PROJECT_ID.svc.id.goog
```

Use Workload Identity Federation for GKE, private networking where needed, Kubernetes RBAC, network policies and controlled image sources.
