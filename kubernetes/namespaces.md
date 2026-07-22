# Kubernetes : Namespaces

## Manage Namespaces

```bash
kubectl get namespaces
kubectl create namespace application
kubectl describe namespace application
kubectl delete namespace application
```

## Namespace Manifest

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: application
  labels:
    environment: production
```

## Use a Namespace

```bash
kubectl get pods -n application
kubectl apply -f manifest.yaml -n application
kubectl delete -f manifest.yaml -n application
```

## Set the Default Namespace

```bash
kubectl config set-context --current --namespace=application
kubectl config view --minify | grep namespace
```

## Resource Quota

```yaml
apiVersion: v1
kind: ResourceQuota
metadata:
  name: application-quota
  namespace: application
spec:
  hard:
    requests.cpu: "4"
    requests.memory: 8Gi
    limits.cpu: "8"
    limits.memory: 16Gi
    pods: "20"
```

## Limit Range

```yaml
apiVersion: v1
kind: LimitRange
metadata:
  name: application-limits
  namespace: application
spec:
  limits:
    - type: Container
      defaultRequest:
        cpu: 100m
        memory: 128Mi
      default:
        cpu: 500m
        memory: 512Mi
```
