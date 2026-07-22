# Kubernetes : Architecture

## Control Plane

- `kube-apiserver`: exposes the Kubernetes API.
- `etcd`: stores cluster state and configuration.
- `kube-scheduler`: assigns unscheduled Pods to Nodes.
- `kube-controller-manager`: runs cluster controllers.
- `cloud-controller-manager`: integrates supported cloud-provider functions.

## Worker Node

- `kubelet`: ensures declared Pods and containers run on the Node.
- Container runtime: starts and manages containers.
- `kube-proxy` or another service proxy implementation: supports Service networking.
- CNI plugin: provides Pod networking.

## Core Objects

```text
Cluster
├── Control Plane
├── Nodes
│   └── Pods
│       └── Containers
├── Workloads
│   ├── Deployments
│   ├── StatefulSets
│   ├── DaemonSets
│   ├── Jobs
│   └── CronJobs
├── Services and Gateway or Ingress
└── Configuration and Storage
```

## Inspect the Cluster

```bash
kubectl cluster-info
kubectl get nodes -o wide
kubectl describe node NODE
kubectl get pods -n kube-system
kubectl api-resources
kubectl api-versions
```

## Object Structure

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: application
  namespace: application
spec:
  replicas: 3
  selector:
    matchLabels:
      app: application
  template:
    metadata:
      labels:
        app: application
    spec:
      containers:
        - name: application
          image: example/application:1.0.0
```
