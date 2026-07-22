# Kubernetes : Security

## Security Context

```yaml
spec:
  securityContext:
    runAsNonRoot: true
    runAsUser: 1000
    runAsGroup: 1000
    fsGroup: 1000
    seccompProfile:
      type: RuntimeDefault
  containers:
    - name: application
      image: example/application:1.0.0
      securityContext:
        allowPrivilegeEscalation: false
        readOnlyRootFilesystem: true
        capabilities:
          drop:
            - ALL
```

## Service Account

```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  name: application
  namespace: application
automountServiceAccountToken: false
```

## Role and RoleBinding

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  name: pod-reader
  namespace: application
rules:
  - apiGroups: [""]
    resources: ["pods"]
    verbs: ["get", "list", "watch"]
---
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: application-pod-reader
  namespace: application
subjects:
  - kind: ServiceAccount
    name: application
    namespace: application
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: Role
  name: pod-reader
```

## Check Permissions

```bash
kubectl auth can-i get pods
kubectl auth can-i list secrets -n application
kubectl auth can-i --list -n application
kubectl auth can-i get pods   --as=system:serviceaccount:application:application   -n application
```

## NetworkPolicy

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: default-deny-ingress
  namespace: application
spec:
  podSelector: {}
  policyTypes:
    - Ingress
```

## Security Checklist

- Use least-privilege RBAC.
- Run containers as non-root.
- Disable privilege escalation.
- Drop unnecessary Linux capabilities.
- Use a read-only root filesystem where possible.
- Define CPU and memory requests and limits.
- Restrict Pod traffic with NetworkPolicies.
- Protect Secrets with encryption at rest and restricted access.
- Pin and scan container images.
- Keep Kubernetes Nodes and control-plane components updated.
