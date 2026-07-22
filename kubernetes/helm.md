# Kubernetes : Helm

## Install Helm

```bash
brew install helm
helm version
helm env
```

## Repositories

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo list
helm repo update
helm search repo nginx
helm show values bitnami/nginx
```

## Install and Upgrade

```bash
helm install application CHART   --namespace application   --create-namespace

helm upgrade --install application CHART   --namespace application   --create-namespace   --values values.yaml   --atomic   --wait
```

## Releases

```bash
helm list --all-namespaces
helm status application -n application
helm history application -n application
helm rollback application REVISION -n application
helm uninstall application -n application
```

## Chart Development

```bash
helm create application
helm lint ./application
helm template application ./application -f values.yaml
helm install application ./application --dry-run --debug
helm package ./application
```

## Override Values

```bash
helm upgrade --install application ./chart   --set image.tag=1.2.0   --set replicaCount=3
```
