# Golink Helm Chart

Helm chart for deploying [Tailscale golink](https://github.com/tailscale/golink) - a private shortlink service for your tailnet.

## Installation

```bash
# Add the chart repository (if published)
helm repo add golink https://sean-m-benson.github.io/golink-k8s-deployment

# Install with custom auth key
helm install golink golink/golink \
  --set tailscale.authKey=tskey-auth-your-key-here

# Or install with values file
helm install golink golink/golink -f values.yaml
```

## Configuration

See [values.yaml](values.yaml) for all configurable options.

### Required Configuration

```yaml
tailscale:
  authKey: "tskey-auth-your-actual-key"
```

Get your auth key from: https://login.tailscale.com/admin/settings/keys

## Source Code

This chart is part of the [golink-k8s-deployment](https://github.com/sean-m-benson/golink-k8s-deployment) repository.