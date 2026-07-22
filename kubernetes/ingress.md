# Kubernetes : Ingress

An Ingress routes HTTP or HTTPS traffic to Services. An Ingress controller must be installed; creating only the Ingress resource does not implement the routing.

## Ingress Manifest

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: application
spec:
  ingressClassName: nginx
  rules:
    - host: application.example.com
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: application
                port:
                  number: 80
```

## TLS

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: application
spec:
  ingressClassName: nginx
  tls:
    - hosts:
        - application.example.com
      secretName: application-tls
  rules:
    - host: application.example.com
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: application
                port:
                  number: 80
```

## Manage Ingresses

```bash
kubectl apply -f ingress.yaml
kubectl get ingress
kubectl get ingressclasses
kubectl describe ingress application
kubectl delete ingress application
```

## Diagnostics

```bash
kubectl get ingress application -o yaml
kubectl get service application
kubectl get endpointslices -l kubernetes.io/service-name=application
kubectl logs -n INGRESS_NAMESPACE deployment/INGRESS_CONTROLLER
```

The Kubernetes project recommends Gateway API for new capabilities; the Ingress API remains available but is frozen.
