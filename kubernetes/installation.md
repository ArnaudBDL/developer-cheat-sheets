# Kubernetes : Installation

## Install kubectl

```bash
# macOS
brew install kubectl

# Verify installation
kubectl version --client
kubectl help
```

## Local Cluster with Minikube

```bash
brew install minikube
minikube start
minikube status
minikube dashboard
minikube stop
minikube delete
```

## Local Cluster with kind

```bash
brew install kind
kind create cluster --name local
kind get clusters
kubectl cluster-info --context kind-local
kind delete cluster --name local
```

## Cluster Access

```bash
kubectl config get-contexts
kubectl config current-context
kubectl config use-context CONTEXT
kubectl cluster-info
kubectl get nodes
```

## Validate Access

```bash
kubectl auth can-i get pods
kubectl get namespaces
kubectl get pods --all-namespaces
kubectl version
```
