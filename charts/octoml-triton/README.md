# octoml-triton

Helm Chart to deploy models accelerated by Octomizer to the Triton inference server.

## Get Repo Info

```console
helm repo add octoml-triton https://octoml.github.io/octoml-helm-charts/octoml-triton
helm repo update
```

## Install Chart

**Important:** only helm3 is supported

```console
helm install [RELEASE_NAME] octoml-triton/octoml-triton
```
## Uninstall Chart

```console
helm uninstall [RELEASE_NAME]
```

This removes all the Kubernetes components associated with the chart and deletes the release.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

## Upgrading Chart

```console
helm upgrade [RELEASE_NAME] [CHART] --install
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| replicas | int | 1 | | Number of Triton pods to deploy
| grpcPort | int | 8001 | Port on Triton pods exposing GRPC endpoint
| httpPort | int | 8000 | Port on Triton pods exposing HTTP endpoint
| imagePullSecret | string | regcred | Name of the image pull secret used to pull the Triton pod image
| imageName | string |
| service.type | string | ClusterIP
| imageCredentials.registry | string |
| imageCredentials.username | string |
| imageCredentials.password | string |
| imageCredentials.email | string |
| prometheus.enabled | bool | true
| prometheus.metricsPort | int | 8002 | Port on which to expose Prometheus endpoint
| prometheus.labels | object | {}
| prometheus.honorLabels | bool | false
| tolerations | object | {}
| nodeSelector | object | {}
