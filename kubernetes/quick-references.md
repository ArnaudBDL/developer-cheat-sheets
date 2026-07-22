# Kubernetes : Quick References

## Context and cluster

```bash
kubectl config get-contexts
kubectl config use-context my-context
kubectl cluster-info
kubectl get nodes
```

## Resources

```bash
kubectl get all -n my-namespace
kubectl get pods -A
kubectl describe pod my-pod -n my-namespace
kubectl apply -f manifest.yaml
kubectl delete -f manifest.yaml
```

## Debugging

```bash
kubectl logs -f my-pod -n my-namespace
kubectl exec -it my-pod -n my-namespace -- sh
kubectl get events -n my-namespace --sort-by=.metadata.creationTimestamp
kubectl port-forward service/my-service 8080:80
```
