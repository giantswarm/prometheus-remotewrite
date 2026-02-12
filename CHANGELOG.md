# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Change team annotation in `Chart.yaml` to OpenContainers format (`io.giantswarm.application.team`).

## [1.4.1] - 2026-01-30

### Changed

- Build with up-to-date pipelines.

## [1.4.0] - 2025-10-02

### Added

- Add tracingConfig to Prometheus if tracing is enabled.

### Changed

- Split up the manifest into smaller ones.

## [1.3.0] - 2025-09-30

### Changed

- Add external label support for loki recording rules.

## [1.2.0] - 2025-08-20

### Changed

- Bumped kube-prometheus-stack to v17.0.0

## [1.1.0] - 2025-07-22

### Added

- Add `app.kubernetes.io/component` label to align with the other mimir components

## [1.0.0] - 2025-05-12

### Changed

- Replace the `repo` renovate marker with  `registry` on the Prometheus image so renovate can detect the new version.
- Upgrade Prometheus to 3.3.0.

### Removed

- Stop pushing the application to vintage clusters.
- Clean up manifest targetting vintage clusters.

## [0.8.1] - 2025-04-17

### Fixed

- Fix home URL in chart metadata

### Changed

- Bumped kube-prometheus-stack to v15.0.0

## [0.8.0] - 2025-03-04

### Changed

- Extract RemoteRead tenant to helm values to be able to override it.

## [0.7.1] - 2025-02-26

### Changed

- Bumped kube-prometheus-stack to v14.0.0

## [0.7.0] - 2025-02-04

### Added

- Add `prometheus` priority class in helm chart's templates.

## [0.6.0] - 2024-10-10

### Added

- Add helm chart templating test in ci pipeline.
- Add tests with ats in ci pipeline.

## [0.5.0] - 2024-10-09

### Removed

- Remove legacy in-house slo framework.

## [0.4.0] - 2024-09-23

### Changed

- Enable `proxyFromEnvironment` property in the `RemoteWrite` of the `mimir-to-grafana-cloud` PrometheusCR.

## [0.3.2] - 2024-09-16

### Removed

- Remove some legacy slo metrics we do not need (slo_errors_per_request:ratio_ratexxx that are not 5m).

## [0.3.1] - 2024-09-04

### Removed

- Remove sloth recording rules being sent to Grafana Cloud as we have too many without aggregations.

## [0.3.0] - 2024-09-02

### Added

- Send sloth recording rules to Grafana Cloud https://github.com/giantswarm/giantswarm/issues/31098.

### Changed

- Clean up some things we do not need with mimir.
- Bump Prometheus version from `2.50.1` to `2.54.1`.

## [0.2.3] - 2024-06-27

### Fixed

- Fix `spec.podMetadata` indentation in `mimir-to-grafana-cloud` Prometheus CR.

## [0.2.2] - 2024-04-16

### Fixed

- Fix `mimir-pometheus` vpa by adding labels and disabling it by default.

## [0.2.1] - 2024-04-16

### Added

- Add vpa for the `mimir-prometheus`.

## [0.2.0] - 2024-03-20

### Changed

- Enable remote write from existing Prometheus to Mimir and from Mimir to grafana cloud using a Prometheus instance in-between to read data from Mimir and send data to Grafana Cloud until https://github.com/grafana/mimir/pull/4575 gets merged.
- Add documentation explaining the architecture of the RemoteWrite in case of Mimir is enabled.

## [0.1.4] - 2024-03-13

### Added

- Enable or disable the remoteWrite feature by setting the `enabled` property. We want to be able to disable this when mimir is deployed.

### Removed

- Stop pushing to `openstack-app-collection`.

## [0.1.3] - 2022-12-19

### Fixed

- Allow insecure skip verify on remote write.

## [0.1.2] - 2022-10-28

## [0.1.1] - 2022-10-20

### Fixed

- Fix `grafana-cloud` secret. No changes, just redeploying with fixed config, see https://github.com/giantswarm/config/pull/1325

## [0.1.0] - 2022-07-13

### Added

- Add `grafana-cloud` remote write configuration.
  Hold configuration for Grafana Cloud remote write endpoint configured at https://grafana.com

[Unreleased]: https://github.com/giantswarm/prometheus-remotewrite/compare/v1.4.1...HEAD
[1.4.1]: https://github.com/giantswarm/prometheus-remotewrite/compare/v1.4.0...v1.4.1
[1.4.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v1.3.0...v1.4.0
[1.3.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.8.1...v1.0.0
[0.8.1]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.8.0...v0.8.1
[0.8.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.7.1...v0.8.0
[0.7.1]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.7.0...v0.7.1
[0.7.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.6.0...v0.7.0
[0.6.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.5.0...v0.6.0
[0.5.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.4.0...v0.5.0
[0.4.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.3.2...v0.4.0
[0.3.2]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.3.1...v0.3.2
[0.3.1]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.3.0...v0.3.1
[0.3.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.2.3...v0.3.0
[0.2.3]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.2.2...v0.2.3
[0.2.2]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.2.1...v0.2.2
[0.2.1]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.2.0...v0.2.1
[0.2.0]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.1.4...v0.2.0
[0.1.4]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.1.3...v0.1.4
[0.1.3]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.1.2...v0.1.3
[0.1.2]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/giantswarm/prometheus-remotewrite/releases/tag/v0.1.0
