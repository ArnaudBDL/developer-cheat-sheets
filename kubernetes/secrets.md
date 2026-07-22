# Kubernetes : Secrets

Secrets hold sensitive values such as passwords, tokens and keys. Base64 encoding is not encryption.

## Create Secrets

```bash
kubectl create secret generic database-credentials   --from-literal=username=application   --from-literal=password='change-me'

kubectl create secret tls application-tls   --cert=certificate.pem   --key=private-key.pem
```

## Manifest with stringData

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: database-credentials
type: Opaque
stringData:
  username: application
  password: change-me
```

## Environment Variables

```yaml
env:
  - name: DATABASE_USERNAME
    valueFrom:
      secretKeyRef:
        name: database-credentials
        key: username
  - name: DATABASE_PASSWORD
    valueFrom:
      secretKeyRef:
        name: database-credentials
        key: password
```

## Volume Mount

```yaml
volumes:
  - name: credentials
    secret:
      secretName: database-credentials
containers:
  - name: application
    image: example/application:1.0.0
    volumeMounts:
      - name: credentials
        mountPath: /run/secrets/database
        readOnly: true
```

## Inspect Safely

```bash
kubectl get secrets
kubectl describe secret database-credentials
kubectl get secret database-credentials -o jsonpath='{.data.username}' | base64 --decode
```

## Security Checklist

- Enable encryption at rest for Secrets.
- Restrict Secret access with least-privilege RBAC.
- Restrict which containers receive each Secret.
- Avoid committing Secret manifests containing real values.
- Consider an external Secret store provider.
