Unseal chart

Installs a Kubernetes CronJob that runs every 2 minutes to perform the "unseal" operation.

Configuration is provided via `values.yaml`. The chart creates an ExternalSecret which uses a ClusterSecretStore (default `bitwarden-notes`) to populate the Kubernetes secret consumed by the CronJob.
