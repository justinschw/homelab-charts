# app-ingress Helm chart

This chart provisions:
- a ClusterIssuer using Let's Encrypt (ACME) with Cloudflare DNS-01 solver
- a Certificate for *.homelab.schwfam.org

Usage:
1. Create the Cloudflare API key secret in the `cert-manager` namespace:

```bash
kubectl -n cert-manager create secret generic cloudflare-api-key --from-literal=api-key='YOUR_CLOUDFLARE_API_KEY'
```

2. Edit `values.yaml` to set your email and target certificate namespace.

3. Install the chart (example):

```bash
helm upgrade --install appingress . -n cert-manager --create-namespace
```

After installation, check the Certificate and the secret in the target namespace.
