# Kubernetes : Troubleshooting

## Cluster Overview

```bash
kubectl cluster-info
kubectl get nodes -o wide
kubectl get pods --all-namespaces -o wide
kubectl get events --all-namespaces --sort-by=.metadata.creationTimestamp
kubectl get componentstatuses
```

## Pod Diagnostics

```bash
kubectl get pod POD -o yaml
kubectl describe pod POD
kubectl logs POD
kubectl logs POD --previous
kubectl logs POD -c CONTAINER
kubectl exec -it POD -- sh
```

## Common Pod States

```text
Pending             Scheduling, capacity, volume or image issue
CrashLoopBackOff    Container repeatedly exits
ImagePullBackOff    Image name, registry or credentials issue
CreateContainerError Configuration, volume or runtime issue
Evicted             Node pressure caused Pod eviction
Terminating         Shutdown, finalizer or storage issue
```

## Deployment Diagnostics

```bash
kubectl describe deployment APPLICATION
kubectl get replicasets
kubectl rollout status deployment/APPLICATION
kubectl rollout history deployment/APPLICATION
kubectl rollout undo deployment/APPLICATION
```

## Service and DNS

```bash
kubectl get service SERVICE -o yaml
kubectl get endpointslices -l kubernetes.io/service-name=SERVICE
kubectl port-forward service/SERVICE 8080:80
kubectl run dns-test --rm -it --restart=Never --image=busybox:1.36 -- nslookup SERVICE
```

## Configuration

```bash
kubectl get configmap CONFIG -o yaml
kubectl describe secret SECRET
kubectl get pod POD -o jsonpath='{.spec.containers[*].env}'
kubectl diff -f manifest.yaml
kubectl apply --dry-run=server -f manifest.yaml
```

## Storage

```bash
kubectl get pvc,pv
kubectl describe pvc CLAIM
kubectl get storageclasses
kubectl describe pod POD
```

## Resource Usage

```bash
kubectl top nodes
kubectl top pods -A
kubectl top pod POD --containers
kubectl describe node NODE
```

## Temporary Debug Container

```bash
kubectl debug -it POD --image=busybox:1.36 --target=CONTAINER
kubectl debug node/NODE -it --image=ubuntu
```
