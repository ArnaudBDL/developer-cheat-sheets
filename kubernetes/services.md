# Kubernetes : Services

## ClusterIP Service

```yaml
apiVersion: v1
kind: Service
metadata:
  name: application
spec:
  type: ClusterIP
  selector:
    app: application
  ports:
    - name: http
      port: 80
      targetPort: 8080
```

## Service Types

- `ClusterIP`: internal virtual IP, default type.
- `NodePort`: exposes the Service on a port of each Node.
- `LoadBalancer`: requests an external load balancer when supported.
- `ExternalName`: maps the Service to an external DNS name.

## Manage Services

```bash
kubectl apply -f service.yaml
kubectl get services
kubectl get service application -o wide
kubectl describe service application
kubectl get endpointslices -l kubernetes.io/service-name=application
kubectl delete service application
```

## Expose a Deployment

```bash
kubectl expose deployment application   --name application   --port 80   --target-port 8080   --type ClusterIP
```

## Port Forward

```bash
kubectl port-forward service/application 8080:80
kubectl port-forward deployment/application 8080:8080
```

## DNS

```text
application
application.application
application.application.svc
application.application.svc.cluster.local
```
