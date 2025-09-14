# Golink Kubernetes Deployment

Kubernetes manifests for deploying [Tailscale golink](https://github.com/tailscale/golink): a shortlink service for your tailnet. Created because I couldn't find good existing Kubernetes deployment examples. I'm not affiliated with tailscale in any capacity, just a fan of their product.

## Quick Deployment

1. **Edit the secret manifest** with your Tailscale auth key:
   
   - Edit manifests/secret.yaml and replace the placeholder with your actual auth key, configured [here](https://login.tailscale.com/admin/settings/keys).
   - You may want to create and assign a tag to your auth key to prevent it from expiring.

3. **Deploy everything**:
   ```bash
   kubectl apply -f manifests/
   ```

## Usage

Once deployed, access your golink service at: `go/`

## Files
- `namespace.yaml`: Namespace for Kubernetes resources
- `pvc.yaml`: Persistent storage for database
- `secret.yaml`: Template for auth key (fill in your key)
- `deployment.yaml`: Main golink deployment

# Notes
- I haven't found a good way to prevent Safari from interpreting go/ URLs as search terms for a search engine. To start, you may need to prefix each go link URL with `http(s)://`. Eventually, once the page is in your browsing history, Safari should give that priority over using it as search terms.
- I did get cert errors in each browser the first time I browsed to the go/ URL using https://, but after the first time they disappeared.
- This works for my personal and home-lab use. YMMV for production use.
