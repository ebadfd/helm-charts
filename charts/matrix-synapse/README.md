# matrix-synapse

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.123.0](https://img.shields.io/badge/AppVersion-1.123.0-informational?style=flat-square)

Matrix reference homeserver

This chart is a fork of  [codeberg.org/wrenix/helm-charts/src/branch/main/matrix-synapse](https://codeberg.org/wrenix/helm-charts/src/branch/main/matrix-synapse)

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| ebadfd |  | <https://ebadfd.tech> |

## Installation

### Add Helm repository

```shell
helm repo add matrix-synapse https://helm.ebadfd.tech
helm repo update
```

## Configuration

The following table lists the configurable parameters of the chart and the default values.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config.bindAddresses | list | `["::"]` | The bind addresses to use for the default listeners |
| config.extraListeners | list | `[]` |  |
| config.extraMainListenerTypes | list | `[]` |  |
| config.reportStats | bool | `false` |  |
| config.trustedKeyServers | list | `[{"server_name":"matrix.org"}]` | A set of trusted servers to contact if another server doesn't respond to a signing key request. |
| config.useStructuredLogging | bool | `false` |  |
| externalPostgresql.database | string | `"synapse"` |  |
| externalPostgresql.extraArgs | object | `{}` | Extra arguments for the database connection ref: https://github.com/matrix-org/synapse/blob/develop/docs/postgres.md#synapse-config |
| externalPostgresql.options | object | `{}` | set extra configuration ref: https://github.com/matrix-org/synapse/blob/develop/docs/postgres.md#synapse-config e.g. txn_limit, allow_unsafe_locale |
| externalPostgresql.port | int | `5432` |  |
| externalPostgresql.username | string | `"synapse"` |  |
| externalRedis.port | int | `6379` |  |
| extraConfig | object | `{}` |  |
| extraLoggers | object | `{}` |  |
| extraSecrets | object | `{}` |  |
| fullnameOverride | string | `nil` | Override the full name of the installed chart. |
| global.image.pullPolicy | string | `nil` | if set it will overwrite all pullPolicy |
| global.image.registry | string | `nil` | if set it will overwrite all registry entries |
| grafana.dashboards.annotations | object | `{}` |  |
| grafana.dashboards.enabled | bool | `false` |  |
| grafana.dashboards.labels.grafana_dashboard | string | `"1"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.registry | string | `"ghcr.io"` |  |
| image.repository | string | `"element-hq/synapse"` |  |
| image.tag | string | `nil` | Overrides the image tag whose default is the chart appVersion. |
| ingress.annotations | object | `{}` |  |
| ingress.csHosts | list | `[]` |  |
| ingress.csPaths | list | `[]` |  |
| ingress.enabled | bool | `true` |  |
| ingress.hosts | list | `[]` |  |
| ingress.includeServerName | bool | `true` |  |
| ingress.includeUnderscoreSynapse | bool | `true` |  |
| ingress.paths | list | `[]` |  |
| ingress.tls | list | `[]` |  |
| ingress.traefikPaths | bool | `false` |  |
| ingress.wkHosts | list | `[]` |  |
| nameOverride | string | `nil` | Override part of the installed name, will still keep release name. |
| persistence.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.annotations | object | `{}` |  |
| persistence.enabled | bool | `true` |  |
| persistence.existingClaim | string | `nil` | A manually managed Persistent Volume and Claim Requires persistence.enabled: true If defined, PVC must be created manually before volume will be bound |
| persistence.hostPath | string | `nil` | Do not create an PVC, direct use hostPath in Pod |
| persistence.size | string | `"10Gi"` |  |
| persistence.storageClass | string | `nil` | Persistent Volume Storage Class If defined, storageClassName: <storageClass> If set to "-", storageClassName: "", which disables dynamic provisioning If undefined (the default) or set to null, no storageClassName spec is   set, choosing the default provisioner.  (gp2 on AWS, standard on   GKE, AWS & OpenStack) |
| postgresql.auth.database | string | `"synapse"` |  |
| postgresql.auth.password | string | `"synapse"` |  |
| postgresql.auth.username | string | `"synapse"` |  |
| postgresql.enabled | bool | `true` |  |
| postgresql.extraArgs | object | `{}` | Extra arguments for the database connection ref: https://github.com/matrix-org/synapse/blob/develop/docs/postgres.md#synapse-config |
| postgresql.options | object | `{}` | set extra configuration ref: https://github.com/matrix-org/synapse/blob/develop/docs/postgres.md#synapse-config e.g. txn_limit, allow_unsafe_locale |
| postgresql.primary.initdb.args | string | `"--lc-collate=C --lc-ctype=C"` |  |
| postgresql.primary.persistence.size | string | `"16Gi"` |  |
| prometheus.podmonitor.enabled | bool | `false` |  |
| prometheus.podmonitor.labels | object | `{}` |  |
| prometheus.rules.additionalRules | list | `[]` |  |
| prometheus.rules.defaults.enabled | bool | `true` |  |
| prometheus.rules.enabled | bool | `false` |  |
| prometheus.rules.labels | object | `{}` |  |
| publicServerName | string | `nil` | The public Matrix server name, this will be used for any public URLs in config as well as for client API links in the ingress. |
| redis.architecture | string | `"standalone"` |  |
| redis.auth.enabled | bool | `true` |  |
| redis.auth.existingSecret | string | `nil` | Or use existing secret with "redis-password" key instead of static password |
| redis.auth.existingSecret | string | `""` | name of an existing secret with Redis credentials (instead of auth.password), must be created ahead of time |
| redis.auth.existingSecretPasswordKey | string | `""` | Password key to be retrieved from existing secret |
| redis.auth.password | string | `"synapse"` | XXX Change me! |
| redis.enabled | bool | `true` |  |
| redis.global.storageClass | string | `""` |  |
| redis.master.persistence.enabled | bool | `true` |  |
| redis.master.service.port | int | `6379` |  |
| redis.replica.persistence.enabled | bool | `true` |  |
| serverName | string | `"matrix.example.com"` | The Matrix domain name, this is what will be used for the domain part in your MXIDs. |
| service.port | int | `8008` |  |
| service.targetPort | string | `"http"` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `false` |  |
| signingkey.annotations | object | `{"helm.sh/hook":"pre-install,pre-upgrade","helm.sh/hook-delete-policy":"before-hook-creation,hook-succeeded"}` | Annotations to apply to the job and rbac for signing-key. |
| signingkey.job.enabled | bool | `true` |  |
| signingkey.job.publishImage.pullPolicy | string | `"IfNotPresent"` |  |
| signingkey.job.publishImage.registry | string | `"docker.io"` |  |
| signingkey.job.publishImage.repository | string | `"bitnami/kubectl"` |  |
| signingkey.job.publishImage.tag | string | `"latest"` |  |
| signingkey.resources | object | `{}` |  |
| synapse.affinity | object | `{}` |  |
| synapse.annotations | object | `{}` |  |
| synapse.extraCommands | list | `[]` |  |
| synapse.extraEnv | list | `[]` |  |
| synapse.extraVolumeMounts | list | `[]` |  |
| synapse.extraVolumes | list | `[]` |  |
| synapse.labels | object | `{}` |  |
| synapse.livenessProbe.httpGet.path | string | `"/health"` |  |
| synapse.livenessProbe.httpGet.port | string | `"http"` |  |
| synapse.nodeSelector | object | `{}` |  |
| synapse.podSecurityContext | object | `{}` |  |
| synapse.readinessProbe.httpGet.path | string | `"/health"` |  |
| synapse.readinessProbe.httpGet.port | string | `"http"` |  |
| synapse.resources | object | `{}` |  |
| synapse.securityContext | object | `{}` |  |
| synapse.startupProbe.failureThreshold | int | `12` |  |
| synapse.startupProbe.httpGet.path | string | `"/health"` |  |
| synapse.startupProbe.httpGet.port | string | `"http"` |  |
| synapse.strategy.type | string | `"RollingUpdate"` |  |
| synapse.tolerations | list | `[]` |  |
| volumePermissions.enabled | bool | `false` |  |
| volumePermissions.gid | int | `666` |  |
| volumePermissions.image.pullPolicy | string | `"Always"` |  |
| volumePermissions.image.registry | string | `"docker.io"` |  |
| volumePermissions.image.repository | string | `"library/alpine"` |  |
| volumePermissions.image.tag | string | `"3.21.2"` |  |
| volumePermissions.resources | object | `{}` |  |
| volumePermissions.uid | int | `666` |  |
| wellknown.affinity | object | `{}` |  |
| wellknown.client | object | `{}` | Data to serve on .well-known/matrix/client.  m.homeserver:    base_url: https://matrix.example.com |
| wellknown.containerPort | int | `80` |  |
| wellknown.element | object | `{}` | Data to serve on .well-known/element/element.json  call:    widget_url: https://call.element.io |
| wellknown.enabled | bool | `false` |  |
| wellknown.env | list | `[]` |  |
| wellknown.image.pullPolicy | string | `"IfNotPresent"` |  |
| wellknown.image.registry | string | `"docker.io"` |  |
| wellknown.image.repository | string | `"library/nginx"` |  |
| wellknown.image.tag | string | `"1.27.3"` |  |
| wellknown.nodeSelector | object | `{}` |  |
| wellknown.podAnnotations | list | `[]` |  |
| wellknown.podLabels | object | `{}` |  |
| wellknown.podSecurityContext | object | `{}` |  |
| wellknown.replicaCount | int | `1` |  |
| wellknown.resources | object | `{}` |  |
| wellknown.securityContext | object | `{}` |  |
| wellknown.server | object | `{}` | The host and port combo to serve on .well-known/matrix/server.  m.server: matrix.example.com:443 |
| wellknown.service.annotations | object | `{}` |  |
| wellknown.service.port | int | `8080` |  |
| wellknown.service.type | string | `"ClusterIP"` |  |
| wellknown.tolerations | list | `[]` |  |
| workers.appservice.enabled | bool | `false` |  |
| workers.appservice.generic | bool | `true` |  |
| workers.appservice.name | string | `"appservices"` |  |
| workers.default.affinity | object | `{}` |  |
| workers.default.annotations | object | `{}` |  |
| workers.default.extraCommands | list | `[]` |  |
| workers.default.extraEnv | list | `[]` |  |
| workers.default.livenessProbe.httpGet.path | string | `"/health"` |  |
| workers.default.livenessProbe.httpGet.port | string | `"metrics"` |  |
| workers.default.nodeSelector | object | `{}` |  |
| workers.default.podSecurityContext | object | `{}` |  |
| workers.default.readinessProbe.httpGet.path | string | `"/health"` |  |
| workers.default.readinessProbe.httpGet.port | string | `"metrics"` |  |
| workers.default.replicaCount | int | `1` |  |
| workers.default.resources | object | `{}` |  |
| workers.default.securityContext | object | `{}` |  |
| workers.default.startupProbe.failureThreshold | int | `6` |  |
| workers.default.startupProbe.httpGet.path | string | `"/health"` |  |
| workers.default.startupProbe.httpGet.port | string | `"metrics"` |  |
| workers.default.strategy.type | string | `"RollingUpdate"` |  |
| workers.default.tolerations | list | `[]` |  |
| workers.default.volumeMounts | list | `[]` |  |
| workers.default.volumes | list | `[]` |  |
| workers.federation_sender.enabled | bool | `false` |  |
| workers.frontend_proxy.csPaths[0] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/keys/upload"` |  |
| workers.frontend_proxy.enabled | bool | `false` |  |
| workers.frontend_proxy.listeners[0] | string | `"client"` |  |
| workers.generic_worker.csPaths[0] | string | `"/_matrix/client/(api/v1|r0|v3)/events$"` |  |
| workers.generic_worker.csPaths[10] | string | `"/_matrix/client/(r0|v3|unstable)/account/3pid$"` |  |
| workers.generic_worker.csPaths[11] | string | `"/_matrix/client/(r0|v3|unstable)/account/whoami$"` |  |
| workers.generic_worker.csPaths[12] | string | `"/_matrix/client/(r0|v3|unstable)/devices$"` |  |
| workers.generic_worker.csPaths[13] | string | `"/_matrix/client/versions$"` |  |
| workers.generic_worker.csPaths[14] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/voip/turnServer$"` |  |
| workers.generic_worker.csPaths[15] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/event/"` |  |
| workers.generic_worker.csPaths[16] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/joined_rooms$"` |  |
| workers.generic_worker.csPaths[17] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/search$"` |  |
| workers.generic_worker.csPaths[18] | string | `"/_matrix/client/(r0|v3|unstable)/keys/query$"` |  |
| workers.generic_worker.csPaths[19] | string | `"/_matrix/client/(r0|v3|unstable)/keys/changes$"` |  |
| workers.generic_worker.csPaths[1] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/createRoom$"` |  |
| workers.generic_worker.csPaths[20] | string | `"/_matrix/client/(r0|v3|unstable)/keys/claim$"` |  |
| workers.generic_worker.csPaths[21] | string | `"/_matrix/client/(r0|v3|unstable)/room_keys/"` |  |
| workers.generic_worker.csPaths[22] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/login$"` |  |
| workers.generic_worker.csPaths[23] | string | `"/_matrix/client/(r0|v3|unstable)/register$"` |  |
| workers.generic_worker.csPaths[24] | string | `"/_matrix/client/v1/register/m.login.registration_token/validity$"` |  |
| workers.generic_worker.csPaths[25] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/redact"` |  |
| workers.generic_worker.csPaths[26] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/send"` |  |
| workers.generic_worker.csPaths[27] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/state/"` |  |
| workers.generic_worker.csPaths[28] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/(join|invite|leave|ban|unban|kick)$"` |  |
| workers.generic_worker.csPaths[29] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/join/"` |  |
| workers.generic_worker.csPaths[2] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/publicRooms$"` |  |
| workers.generic_worker.csPaths[30] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/profile/"` |  |
| workers.generic_worker.csPaths[31] | string | `"/_matrix/client/(r0|v3|unstable)/user_directory/search"` |  |
| workers.generic_worker.csPaths[3] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/joined_members$"` |  |
| workers.generic_worker.csPaths[4] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/context/"` |  |
| workers.generic_worker.csPaths[5] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/members$"` |  |
| workers.generic_worker.csPaths[6] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/rooms/.*/state$"` |  |
| workers.generic_worker.csPaths[7] | string | `"/_matrix/client/v1/rooms/.*/hierarchy$"` |  |
| workers.generic_worker.csPaths[8] | string | `"/_matrix/client/unstable/org.matrix.msc2716/rooms/.*/batch_send$"` |  |
| workers.generic_worker.csPaths[9] | string | `"/_matrix/client/unstable/im.nheko.summary/rooms/.*/summary$"` |  |
| workers.generic_worker.enabled | bool | `false` |  |
| workers.generic_worker.generic | bool | `true` |  |
| workers.generic_worker.listeners[0] | string | `"client"` |  |
| workers.generic_worker.listeners[1] | string | `"federation"` |  |
| workers.generic_worker.paths[0] | string | `"/_matrix/federation/v1/event/"` |  |
| workers.generic_worker.paths[10] | string | `"/_matrix/federation/(v1|v2)/send_leave/"` |  |
| workers.generic_worker.paths[11] | string | `"/_matrix/federation/(v1|v2)/invite/"` |  |
| workers.generic_worker.paths[12] | string | `"/_matrix/federation/v1/event_auth/"` |  |
| workers.generic_worker.paths[13] | string | `"/_matrix/federation/v1/exchange_third_party_invite/"` |  |
| workers.generic_worker.paths[14] | string | `"/_matrix/federation/v1/user/devices/"` |  |
| workers.generic_worker.paths[15] | string | `"/_matrix/key/v2/query"` |  |
| workers.generic_worker.paths[16] | string | `"/_matrix/federation/v1/hierarchy/"` |  |
| workers.generic_worker.paths[17] | string | `"/_matrix/federation/v1/send/"` |  |
| workers.generic_worker.paths[1] | string | `"/_matrix/federation/v1/state/"` |  |
| workers.generic_worker.paths[2] | string | `"/_matrix/federation/v1/state_ids/"` |  |
| workers.generic_worker.paths[3] | string | `"/_matrix/federation/v1/backfill/"` |  |
| workers.generic_worker.paths[4] | string | `"/_matrix/federation/v1/get_missing_events/"` |  |
| workers.generic_worker.paths[5] | string | `"/_matrix/federation/v1/publicRooms"` |  |
| workers.generic_worker.paths[6] | string | `"/_matrix/federation/v1/query/"` |  |
| workers.generic_worker.paths[7] | string | `"/_matrix/federation/v1/make_join/"` |  |
| workers.generic_worker.paths[8] | string | `"/_matrix/federation/v1/make_leave/"` |  |
| workers.generic_worker.paths[9] | string | `"/_matrix/federation/(v1|v2)/send_join/"` |  |
| workers.media_repository.csPaths[0] | string | `"/_matrix/media/.*"` |  |
| workers.media_repository.csPaths[1] | string | `"/_synapse/admin/v1/purge_media_cache$"` |  |
| workers.media_repository.csPaths[2] | string | `"/_synapse/admin/v1/room/.*/media"` |  |
| workers.media_repository.csPaths[3] | string | `"/_synapse/admin/v1/user/.*/media"` |  |
| workers.media_repository.csPaths[4] | string | `"/_synapse/admin/v1/media/"` |  |
| workers.media_repository.csPaths[5] | string | `"/_synapse/admin/v1/quarantine_media/"` |  |
| workers.media_repository.csPaths[6] | string | `"/_synapse/admin/v1/users/.*/media$"` |  |
| workers.media_repository.enabled | bool | `false` |  |
| workers.media_repository.listeners[0] | string | `"media"` |  |
| workers.media_repository.paths[0] | string | `"/_matrix/media/.*"` |  |
| workers.pusher.enabled | bool | `false` |  |
| workers.user_dir.csPaths[0] | string | `"/_matrix/client/(api/v1|r0|v3|unstable)/user_directory/search$"` |  |
| workers.user_dir.enabled | bool | `false` |  |
| workers.user_dir.listeners[0] | string | `"client"` |  |
| workers.user_dir.name | string | `"userdir"` |  |
