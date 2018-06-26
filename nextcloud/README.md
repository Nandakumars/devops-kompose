# Nextcloud

This is a yet another Nextcloud Helm chart.

Alternative for https://github.com/kubernetes/charts/pull/5180.


## Prerequisites

- Kubernetes 1.8+ with Beta APIs enabled
- PV provisioner support in the underlying infrastructure


## Getting Started

To install the chart with the release name `nextcloud`:

```sh
helm install ./nextcloud --name nextcloud
```

To delete the release `nextcloud`:

```sh
helm delete nextcloud
```


## Configuration

The following table lists the configurable parameters of the chart and their default values.

Parameter | Description | Default
----------|-------------|--------
`nextcloud.host` | Hostname. | `nextcloud.example.com`
`persistence.enabled` | Create a persistent volume to store data. | `true`
`persistence.size` | Size of a persistent volume. | `8Gi`
`persistence.storageClass` | Type of a persistent volume. | `nil`
`persistence.existingClaim` | Name of the existing persistent volume. | `nil`
`ingress.enabled` |	Enable ingress controller resource.	| `false`
`ingress.hosts`	| Hostnames. | `[nextcloud.example.com]`
`resources.limits` | Pod resource limits. | `{}`
`resources.requests` | Pod resource requests. | `{}`
`nodeSelector` | Node labels for pod assignment | `{}`


### Resources Limits

TODO


### Persistence

This chart creates a `PersistentVolumeClaim` with 8GB volume by default.
You can set size as follows:

```yaml
# values.yaml
persistence:
  size: 100Gi
```


## Upgrade Mattermost

To upgrade to a more recent version of Mattermost:

```sh
helm upgrade nextcloud
```
