kind create cluster --config=cluster-config.yaml
helm repo add nats https://nats-io.github.io/k8s/helm/charts/
helm repo update
helm show values nats/nats > values.yaml
helm install -f values.yaml kind-cluster-nats nats/nats
