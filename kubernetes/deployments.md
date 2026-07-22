# Kubernetes : Deployments

## Deployment Manifest

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: application
spec:
  replicas: 3
  selector:
    matchLabels:
      app: application
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxUnavailable: 0
      maxSurge: 1
  template:
    metadata:
      labels:
        app: application
    spec:
      containers:
        - name: application
          image: example/application:1.0.0
          ports:
            - containerPort: 8080
          resources:
            requests:
              cpu: 100m
              memory: 128Mi
            limits:
              cpu: 500m
              memory: 512Mi
```

## Manage Deployments

```bash
kubectl apply -f deployment.yaml
kubectl get deployments
kubectl describe deployment application
kubectl delete deployment application
```

## Scale

```bash
kubectl scale deployment application --replicas=5
kubectl get deployment application
kubectl get replicasets
```

## Rollout

```bash
kubectl set image deployment/application application=example/application:1.1.0
kubectl rollout status deployment/application
kubectl rollout history deployment/application
kubectl rollout undo deployment/application
kubectl rollout undo deployment/application --to-revision=2
kubectl rollout restart deployment/application
```

## Wait for Availability

```bash
kubectl wait --for=condition=available deployment/application --timeout=120s
```
