# Kubernetes : ConfigMaps

ConfigMaps hold non-confidential configuration as key-value data. Use Secrets for confidential values.

## Create ConfigMaps

```bash
kubectl create configmap application-config   --from-literal=APP_ENV=production   --from-literal=LOG_LEVEL=info

kubectl create configmap application-files   --from-file=application.yaml

kubectl create configmap application-directory   --from-file=./config/
```

## Manifest

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: application-config
data:
  APP_ENV: production
  LOG_LEVEL: info
  application.yaml: |
    server:
      port: 8080
```

## Environment Variables

```yaml
envFrom:
  - configMapRef:
      name: application-config
```

```yaml
env:
  - name: APP_ENV
    valueFrom:
      configMapKeyRef:
        name: application-config
        key: APP_ENV
```

## Volume Mount

```yaml
volumes:
  - name: configuration
    configMap:
      name: application-config
containers:
  - name: application
    image: example/application:1.0.0
    volumeMounts:
      - name: configuration
        mountPath: /app/config
        readOnly: true
```

## Inspect

```bash
kubectl get configmaps
kubectl describe configmap application-config
kubectl get configmap application-config -o yaml
kubectl delete configmap application-config
```
