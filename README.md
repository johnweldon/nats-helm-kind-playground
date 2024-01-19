# setup

## kind cluster

```sh
kind create cluster --config=cluster-config.yaml
```

## helm

```sh
helm repo add nats https://nats-io.github.io/k8s/helm/charts/
helm repo update
helm show values nats/nats > values.yaml
```

## install chart

```sh
helm install -f values.yaml kind-cluster-nats nats/nats
```

## upgrade chart

```sh
helm upgrade -f values.yaml kind-cluster-nats nats/nats
```

# cleanup

## uninstall chart

```sh
helm uninstall kind-cluster-nats
```

## remove cluster

```sh
kind delete cluster --name kind-cluster-nats
```
