# Homer

<img src="https://raw.githubusercontent.com/bastienwirtz/homer/5609315/public/assets/icons/logo.svg" align="right" width="92" alt="homer logo">

![Version: 0.13.0](https://img.shields.io/badge/Version-0.13.0-informational?style=flat)
![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat)
![AppVersion: v25.02.1](https://img.shields.io/badge/AppVersion-v25.02.1-informational?style=flat)

A dead simple static HOMepage for your servER to keep your services on hand, from a simple yaml configuration file.

**Homepage:** <https://charts.gabe565.com/charts/homer/>

**This chart is not maintained by the upstream project and any issues with the chart should be raised
[here](https://github.com/gabe565/charts/issues/new?assignees=gabe565&labels=bug&template=bug_report.yaml&name=homer&version=0.13.0)**

## Source Code

* <https://github.com/bastienwirtz/homer>

## Requirements

Kubernetes: `>=1.22.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| <https://bjw-s-labs.github.io/helm-charts> | common | 1.5.1 |

## Installing the Chart

To install the chart with the release name `homer`

### OCI (Recommended)

```console
helm install homer oci://ghcr.io/gabe565/charts/homer
```

### Traditional

```console
helm repo add gabe565 https://charts.gabe565.com
helm repo update
helm install homer gabe565/homer
```

## Uninstalling the Chart

To uninstall the `homer` deployment

```console
helm uninstall homer
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/bjw-s/helm-charts/tree/a081de5/charts/library/common/values.yaml) from the [bjw-s common library](https://github.com/bjw-s/helm-charts/tree/a081de5/charts/library/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install homer \
  --set env.TZ="America/New York" \
    gabe565/homer
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install homer gabe565/homer -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from the bjw-s common library chart [here](https://github.com/bjw-s/helm-charts/tree/a081de5/charts/library/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| addons.codeserver.enabled | bool | `false` | Enable VS Code server addon.    This allows for easy access to assets. |
| addons.codeserver.ingress | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the VS Code server under this key. |
| configMaps.config.data | object | See [values.yaml](./values.yaml) | Homer configuration. [[ref]](https://github.com/bastienwirtz/homer/blob/main/docs/configuration.md) |
| configMaps.config.enabled | bool | `false` | Store homer configuration as a ConfigMap |
| controller.strategy | string | `"RollingUpdate"` | Set the controller upgrade strategy |
| env | object | See [values.yaml](./values.yaml) | environment variables. |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/bastienwirtz/homer"` | image repository |
| image.tag | string | `"v25.02.1"` | image tag |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config | object | See [values.yaml](./values.yaml) | Configure persistence settings for the chart under this key. |
| service.main | object | See [values.yaml](./values.yaml) | Configures service settings for the chart. |

---
Autogenerated from chart metadata using [helm-docs](https://github.com/norwoodj/helm-docs)
