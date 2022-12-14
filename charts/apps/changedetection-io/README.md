# changedetection-io

![Version: 1.5.2](https://img.shields.io/badge/Version-1.5.2-informational?style=flat-square) ![AppVersion: 0.39.4](https://img.shields.io/badge/AppVersion-0.39.4-informational?style=flat-square)

changedetection-io helm package

Chart taken from k8s-at-home repo [here](https://github.com/k8s-at-home/charts/tree/master/charts/incubator/homer).

## Source Code

* <https://github.com/dgtlmoon/changedetection.io>
* <https://github.com/zekker6/charts/tree/master/charts/apps/changedetection-io>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository                             | Name   | Version |
|----------------------------------------|--------|---------|
| https://library-charts.k8s-at-home.com | common | 4.5.2   |

## TL;DR

```console
helm repo add zekker6 https://zekker6.github.io/helm-charts
helm repo update
helm install changedetection-io zekker6/changedetection-io
```

## Installing the Chart

To install the chart with the release name `changedetection-io`

```console
helm install changedetection-io zekker6/changedetection-io
```

## Uninstalling the Chart

To uninstall the `changedetection-io` deployment

```console
helm uninstall changedetection-io
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes
the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from
the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from
the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install changedetection-io \
  --set env.TZ="America/New York" \
    k8s-at-home/changedetection-io
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the
chart.

```console
helm install changedetection-io k8s-at-home/changedetection-io -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library
chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key              | Type   | Default                                 | Description                                                                                                                           |
|------------------|--------|-----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| env              | object | See below                               | environment variables. See more environment variables in the [changedetection-io documentation](https://changedetection-io.org/docs). |
| env.TZ           | string | `"UTC"`                                 | Set the container timezone                                                                                                            |
| image.pullPolicy | string | `"IfNotPresent"`                        | image pull policy                                                                                                                     |
| image.repository | string | `"ghcr.io/dgtlmoon/changedetection.io"` | image repository                                                                                                                      |
| image.tag        | string | `"0.39.4"`                              | image tag                                                                                                                             |
| ingress.main     | object | See values.yaml                         | Enable and configure ingress settings for the chart under this key.                                                                   |
| persistence      | object | See values.yaml                         | Configure persistence settings for the chart under this key.                                                                          |
| service          | object | See values.yaml                         | Configures service settings for the chart.                                                                                            |
