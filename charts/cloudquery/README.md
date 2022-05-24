# cloudquery

![Version: 0.2.3](https://img.shields.io/badge/Version-0.2.3-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.24](https://img.shields.io/badge/AppVersion-0.24-informational?style=flat-square)

The open-source cloud asset inventory powered by SQL.

**Homepage:** <https://cloudquery.io>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| yevgenypats | <yp@cloudquery.io> |  |

## Source Code

* <https://github.com/cloudquery/helm-charts/tree/main/charts/cloudquery>

## Requirements

Kubernetes: `^1.8.0-0`

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config | string | The chart will use a default CloudQuery aws config | CloudQuery config.hcl content |
| containerSecurityContext.enabled | bool | `true` |  |
| containerSecurityContext.runAsUser | int | `1001` |  |
| envRenderSecret | object | `{}` | Sensible environment variables that will be rendered as new secret object This can be useful for auth tokens, etc Make sure not to commit sensitive values to git!! Better use AWS Secret manager (or any other) |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.registry | string | `"ghcr.io"` |  |
| image.repository | string | `"cloudquery/cloudquery"` |  |
| nameOverride | string | `""` | Partially override common.names.fullname template (will maintain the release name) |
| schedule | string | `"0 0 * * *"` | Schedule fetch time Every day at 00:00. More information at: https://crontab.guru/#0_0_*_*_* |
| securityContext.enabled | bool | `true` |  |
| securityContext.fsGroup | int | `1001` |  |
| serviceAccount | object | `{"annotations":{},"autoMount":false,"enabled":false,"name":""}` | Pod Service Account ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/ |
| serviceAccount.annotations | object | `{}` | Additional custom annotations for the ServiceAccount to associate an AWS IAM role with service-account you need to add the following annotations. For more info checkout: https://docs.aws.amazon.com/eks/latest/userguide/specify-service-account-role.html eks.amazonaws.com/role-arn: arn:aws:iam::ACCOUNT_ID:role/ROLE |
| serviceAccount.autoMount | bool | `false` | Auto-mount the service account token in the pod |
| serviceAccount.enabled | bool | `false` | Enable service account (Note: Service Account will only be automatically created if `serviceAccount.name` is not set) |
| serviceAccount.name | string | `""` | Name of an already existing service account. Setting this value disables the automatic service account creation |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.8.1](https://github.com/norwoodj/helm-docs/releases/v1.8.1)