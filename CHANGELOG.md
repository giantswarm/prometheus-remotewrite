# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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

[Unreleased]: https://github.com/giantswarm/prometheus-remotewrite/compare/v0.3.0...HEAD
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
