# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased] - 2023-03-14

### Added

- added WIP Dashboards which Splits Network ansd Satellite overview


## [2.1.0] - 2023-03-14

### Added

- added Timezone variable storj_stats_timezone for Proxy
- added Metric storage_total_bytes_after_expansion
- added Metric storage_free_capacity_estimate_vetted_byte
- added Metric active_wallets
- added Metric payout

### Changed

- Updated Description of storj_stats_storage_remote_segments_lost

## [2.0.0] - 2021-06-21

### Added

- added VictoriaMetrics as TSDB and Scraper

### Fixed

- fixed wrong exporter config for nodestats

### Changed

- changed default max memory for Grafana

### Removed

- removed Prometheus

## [1.0.0] - 2021-06-17

### Added

- initial Version

[Unreleased]: https://github.com/toconspiracy/storj-stats/compare/3.0.0...HEAD
[3.0.0]: https://github.com/toconspiracy/storj-stats/releases/tag/3.0.0
[2.0.0]: https://github.com/toconspiracy/storj-stats/releases/tag/2.0.0
[1.0.0]: https://github.com/toconspiracy/storj-stats/releases/tag/1.0.0