# Nginx Helm Chart

A production-ready Helm chart for deploying Nginx on Kubernetes.

## Features

- Nginx deployment with configurable replicas
- Service exposure (LoadBalancer, ClusterIP, NodePort)
- Liveness and readiness probes
- Resource limits and requests
- Support for node selectors, affinity, and tolerations
- Ingress support (disabled by default)

## Installation

```bash
helm install nginx ./nginx-helm
```

## Upgrade

```bash
helm upgrade nginx ./nginx-helm
```

## Customization

Override default values using the `-f` flag:

```bash
helm install nginx ./nginx-helm -f custom-values.yaml
```

### Common Values to Override

- `replicaCount`: Number of Nginx replicas (default: 3)
- `image.repository`: Docker image repository (default: nginx)
- `image.tag`: Docker image tag (default: 1.24.0)
- `service.type`: Service type - LoadBalancer, ClusterIP, NodePort (default: LoadBalancer)
- `service.port`: Service port (default: 80)

## Example Usage

```bash
# Deploy with 2 replicas
helm install nginx ./nginx-helm --set replicaCount=2

# Use ClusterIP service instead of LoadBalancer
helm install nginx ./nginx-helm --set service.type=ClusterIP

# Enable ingress
helm install nginx ./nginx-helm --set ingress.enabled=true
```

## Cleanup

```bash
helm uninstall nginx
```
