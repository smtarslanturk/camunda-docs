---
id: announcements
title: "Announcements"
description: "Important announcements including deprecation & removal notices"
---

## Camunda Platform 8.2

Release date: 11th of April 2023

End of maintenance: 8th of October 2024

[Release notes](https://github.com/camunda/camunda-platform/releases/tag/8.2.0)
[Release blog](https://camunda.com/blog/2023/04/camunda-platform-8-2-key-to-scaling-automation/)

### OpenSearch 1.3.x support

- Operate version 8.2+ now also support OpenSearch 1.3.x.

## Camunda Platform 8.1

Release date: 11th of October 2022

End of maintenance: 10th of April 2024

[Release notes](https://github.com/camunda/camunda-platform/releases/tag/8.1.0)
[Release blog](https://camunda.com/blog/2022/10/camunda-platform-8-1-released-whats-new/)

## Camunda Platform 8.0

Release date: 12th of April 2022

End of maintenance: 11th of October 2023

[Release notes](https://github.com/camunda/camunda-platform/releases/tag/8.0.0)
[Release blog](https://camunda.com/blog/2022/04/camunda-platform-8-0-released-whats-new/)

### Camunda Platform 8.0.15 release is skipped

The `Camunda Platform 8.0.15` release pipeline lead to corrupted `Zeebe 8.0.15` artifacts getting published.
The whole [Camunda Platform 8.0.15 release](https://github.com/camunda/camunda-platform/releases/tag/8.0.15) was thus skipped and updates from `Camunda Platform 8.0.14` should go straight to `Camunda Platform 8.0.16`.

## Deprecated in 8.0

The [DeployProcess RPC](/apis-tools/grpc.md#deployprocess-rpc) was deprecated in 8.0.
It is replaced by the [DeployResource RPC](/apis-tools/grpc.md#deployresource-rpc).

### Camunda Cloud 1.3

Release date: 11th of January 2022

Camunda Cloud is out of maintenance.

#### Deprecated in 1.3

The `zeebe-test` module was deprecated in 1.3.0. We are currently planning to remove `zeebe-test` for the 1.4.0 release.

### Camunda Cloud 1.2

Release date: 12th of October 2021

Camunda Cloud is out of maintenance.

### Camunda Cloud 1.1

Release date: 13th of July 2021

Camunda Cloud is out of maintenance.

### Camunda Cloud 1.0

Release date: 11th of May 2021

Camunda Cloud is out of maintenance.

#### Removed in 1.0

The support for YAML processes was removed as of release 1.0. The `resourceType` in Deployment record and Process grpc request are deprecated; they will always contain `BPMN` as value.

### Zeebe 0.26.0

#### Deprecated in 0.26.0

##### YAML workflows descriptions

YAML workflows are an alternative way to specify simple workflows using a proprietary YAML description. This feature is deprecated and no longer advertised in the documentation. YAML workflows gained little traction with users and we do not intend to support them in the future.

We recommend all users of YAML workflows to migrate to BPMN workflows as soon as possible. The feature will eventually be removed completely, though the date when this will occur has yet to be defined.

### Zeebe 0.23.0-alpha2

#### Deprecated in 0.23.0-alpha2

- TOML configuration - deprecated and removed in 0.23.0-alpha2
- Legacy environment variables - deprecated in 0.23.0-alpha2, removed in 0.25.0

New configuration:

```yaml
exporters:
  elasticsearch:
    className: io.camunda.zeebe.exporter.ElasticsearchExporter
  debughttp:
    className: io.camunda.zeebe.broker.exporter.debug.DebugHttpExporter
```

In terms of specifying values, there were two minor changes:

- Memory sizes are now specified like this: `512MB` (old way: `512M`)
- Durations (e.g. timeouts) can now also be given in ISO-8601 Durations format. However, you can still use the established method and specify a timeout of `30s`