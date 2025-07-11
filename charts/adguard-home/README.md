# AdGuard Home

<img src="https://raw.githubusercontent.com/gabe565/charts/main/charts/adguard-home/icon.svg" align="right" width="92" alt="adguard-home logo">

![Version: 0.3.25](https://img.shields.io/badge/Version-0.3.25-informational?style=flat)
![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat)
![AppVersion: v0.107.56](https://img.shields.io/badge/AppVersion-v0.107.56-informational?style=flat)

Free and open source, powerful network-wide ads & trackers blocking DNS server.

**Homepage:** <https://charts.gabe565.com/charts/adguard-home/>

**This chart is not maintained by the upstream project and any issues with the chart should be raised
[here](https://github.com/gabe565/charts/issues/new?assignees=gabe565&labels=bug&template=bug_report.yaml&name=adguard-home&version=0.3.25)**

## Source Code

* <https://github.com/AdguardTeam/AdGuardHome>

## Requirements

Kubernetes: `>=1.22.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| <https://bjw-s-labs.github.io/helm-charts> | common | 1.5.1 |

## Installing the Chart

To install the chart with the release name `adguard-home`

### OCI (Recommended)

```console
helm install adguard-home oci://ghcr.io/gabe565/charts/adguard-home
```

### Traditional

```console
helm repo add gabe565 https://charts.gabe565.com
helm repo update
helm install adguard-home gabe565/adguard-home
```

## Uninstalling the Chart

To uninstall the `adguard-home` deployment

```console
helm uninstall adguard-home
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/bjw-s/helm-charts/tree/a081de5/charts/library/common/values.yaml) from the [bjw-s common library](https://github.com/bjw-s/helm-charts/tree/a081de5/charts/library/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install adguard-home \
  --set env.TZ="America/New York" \
    gabe565/adguard-home
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install adguard-home gabe565/adguard-home -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from the bjw-s common library chart [here](https://github.com/bjw-s/helm-charts/tree/a081de5/charts/library/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config | string | See [values.yaml](./values.yaml) | Default AdGuard Home config file.    This will only be copied if an existing config does not exist.    [[ref]](https://github.com/AdguardTeam/AdGuardHome/wiki/Configuration) |
| env.TZ | string | `"UTC"` | Set the container timezone |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.repository | string | `"adguard/adguardhome"` | Image repository |
| image.tag | string | `"v0.107.56"` | Image tag |
| ingress.main | object | See [values.yaml](./values.yaml) | Enable and configure ingress settings for the chart under this key. |
| persistence.config | object | See [values.yaml](./values.yaml) | Configure config persistence settings for the chart under this key. |
| persistence.data | object | See [values.yaml](./values.yaml) | Configure data persistence settings for the chart under this key. |
| service.dns-tcp | object | See [values.yaml](./values.yaml) | Configures settings for the TCP DNS service. |
| service.dns-udp | object | See [values.yaml](./values.yaml) | Configures settings for the UDP DNS service. |
| service.main | object | See [values.yaml](./values.yaml) | Configures settings for the main service. |

---
Autogenerated from chart metadata using [helm-docs](https://github.com/norwoodj/helm-docs)
