# Kubernetes : Storage

## PersistentVolumeClaim

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: application-data
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 10Gi
  storageClassName: standard
```

## Mount a Claim

```yaml
spec:
  volumes:
    - name: application-data
      persistentVolumeClaim:
        claimName: application-data
  containers:
    - name: application
      image: example/application:1.0.0
      volumeMounts:
        - name: application-data
          mountPath: /app/data
```

## Ephemeral Volume

```yaml
spec:
  volumes:
    - name: cache
      emptyDir:
        sizeLimit: 1Gi
  containers:
    - name: application
      image: example/application:1.0.0
      volumeMounts:
        - name: cache
          mountPath: /app/cache
```

## Inspect Storage

```bash
kubectl get storageclasses
kubectl get persistentvolumes
kubectl get persistentvolumeclaims
kubectl describe pvc application-data
kubectl get pvc application-data -o yaml
```

## Access Modes

```text
ReadWriteOnce      Mounted read-write by a single Node
ReadOnlyMany       Mounted read-only by multiple Nodes
ReadWriteMany      Mounted read-write by multiple Nodes
ReadWriteOncePod   Mounted read-write by a single Pod
```

## Delete Carefully

```bash
kubectl delete pvc application-data
kubectl get pv
```

Check the PersistentVolume reclaim policy before deleting a claim that contains required data.
