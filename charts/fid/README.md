# fid

A Helm chart for managing Argo CD RadiantOne Applications and Projects

To regenerate this document, from the root of this chart directory run:
```shell
docker run --rm --volume "$(pwd):/helm-docs" -u $(id -u) jnorwood/helm-docs:latest
```

## Prerequisites

- Helm v3.0.0+
- CRDs (Application and AppProject)
  - You need to install them via [argo-cd Helm chart](../argo-cd) or upstream.

## Installation

```console
helm repo add r1-argocd https://pgodey.github.io/r1-argo-apps
helm install my-release r1-argocd/fid
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| applications[0].destination.namespace | string | `"fid-dev"` |  |
| applications[0].destination.server | string | `"https://kubernetes.default.svc"` |  |
| applications[0].name | string | `"fid-dev"` |  |
| applications[0].project | string | `"default"` |  |
| applications[0].source.chart | string | `"fid"` |  |
| applications[0].source.helm.parameters[0].name | string | `"fid.license"` |  |
| applications[0].source.helm.parameters[0].value | string | `"[FID License Key]"` |  |
| applications[0].source.helm.parameters[1].name | string | `"fid.rootPassword"` |  |
| applications[0].source.helm.parameters[1].value | string | `"R@diant1R0cks"` |  |
| applications[0].source.helm.parameters[2].name | string | `"dependencies.zookeeper"` |  |
| applications[0].source.helm.parameters[2].value | string | `"true"` |  |
| applications[0].source.helm.parameters[3].name | string | `"replicaCount"` |  |
| applications[0].source.helm.parameters[3].value | string | `"2"` |  |
| applications[0].source.repoURL | string | `"https://radiantlogic-devops.github.io/helm"` |  |
| applications[0].source.targetRevision | string | `"0.1.4"` |  |
| applications[0].syncPolicy.automated.prune | bool | `true` |  |
| applications[0].syncPolicy.automated.selfHeal | bool | `true` |  |
| applications[0].syncPolicy.syncOptions[0] | string | `"CreateNamespace=true"` |  |

