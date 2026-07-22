# Kubernetes : Pods

## Pod Manifest

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: application
  labels:
    app: application
spec:
  containers:
    - name: application
      image: nginx:alpine
      ports:
        - containerPort: 80
      resources:
        requests:
          cpu: 100m
          memory: 128Mi
        limits:
          cpu: 500m
          memory: 256Mi
```

## Manage Pods

```bash
kubectl apply -f pod.yaml
kubectl get pods
kubectl get pods -o wide
kubectl describe pod application
kubectl delete pod application
```

## Execute and Copy

```bash
kubectl exec application -- COMMAND
kubectl exec -it application -- sh
kubectl exec -it application -c CONTAINER -- sh
kubectl cp local-file application:/path/file
kubectl cp application:/path/file local-file
```

## Logs

```bash
kubectl logs application
kubectl logs -f application
kubectl logs application -c CONTAINER
kubectl logs application --previous
kubectl logs application --tail=100
kubectl logs application --since=30m
```

## Probes

```yaml
livenessProbe:
  httpGet:
    path: /health/live
    port: 8080
  initialDelaySeconds: 15
  periodSeconds: 10
readinessProbe:
  httpGet:
    path: /health/ready
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 5
startupProbe:
  httpGet:
    path: /health/startup
    port: 8080
  failureThreshold: 30
  periodSeconds: 10
```
