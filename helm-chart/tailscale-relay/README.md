# tailscale-relay

![Version: 0.0.14](https://img.shields.io/badge/Version-0.0.14-informational?style=flat-square) ![AppVersion: v1.14.3](https://img.shields.io/badge/AppVersion-v1.14.3-informational?style=flat-square)

Deploy a tailscale relay on top of kubernetes

**Homepage:** <https://github.com/mvisonneau/tailscale-relay-over-k8s>

## Maintainers

| Name       | Email                      | Url |
|------------|----------------------------|-----|
| mvisonneau | maxime.visonneau@gmail.com |     |

## Source Code

* <https://github.com/mvisonneau/helm-charts/tree/main/charts/tailscale-relay-over-k8s>

## Values

| Key                                 | Type   | Default                                          | Description                                                                                                                                    |
|-------------------------------------|--------|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| affinity                            | object | `{}`                                             |                                                                                                                                                |
| annotations                         | object | `{}`                                             | Additional annotations to add to all resources                                                                                                 |
| config.authKey                      | string | `"foo"`                                          |                                                                                                                                                |
| config.variables                    | object | `{}`                                             |                                                                                                                                                |
| hostNetwork                         | bool   | `false`                                          |                                                                                                                                                |
| image.pullPolicy                    | string | `"IfNotPresent"`                                 |                                                                                                                                                |
| image.repository                    | string | `"docker.io/mvisonneau/tailscale"`               |                                                                                                                                                |
| labels                              | object | `{}`                                             | Additional labels to add to all resources                                                                                                      |
| nodeSelector                        | object | `{}`                                             |                                                                                                                                                |
| podAnnotations                      | object | `{}`                                             | Additional annotations for the pods                                                                                                            |
| podLabels                           | object | `{}`                                             | Additional labels for the pods                                                                                                                 |
| rbac                                | object | `{"enabled":false,"serviceAccount":{"name":""}}` | If your kubernetes cluster defined the pod security policy, then you need to enable this part, and define clusterRole based on your situation. |
| replicas                            | int    | `1`                                              |                                                                                                                                                |
| resources                           | object | `{}`                                             |                                                                                                                                                |
| securityContext.capabilities.add[0] | string | `"NET_ADMIN"`                                    |                                                                                                                                                |
| tolerations                         | list   | `[]`                                             |                                                                                                                                                |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
