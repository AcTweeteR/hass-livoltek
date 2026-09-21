# Changelog

## 1.0.2

- Added complete Spanish user documentation for installation, configuration,
  sensors, diagnostics, maintenance and development.
- Clarified HACS installation, configuration, updates and support documentation.
- Clarified that this repository distributes a Home Assistant custom integration,
  not a Home Assistant App/add-on.
- Added descriptions for the repository areas, workflows, tests, scripts and
  development configuration.
- Added security guidance for reporting issues and protecting cloud credentials.

## 1.0.1

- Removed unused imports reported by Ruff.
- Added the repository topics required by HACS validation.

## 1.0.0

- Initial public AcTweeteR release of the maintained Livoltek adaptation.
- Updated Home Assistant config-flow typing and async API calls.
- Added defensive API timeouts and response validation.
- Preserved the last valid values when Livoltek returns no data temporarily.
- Added token refresh recovery after repeated empty device responses.
- Added daily grid and solar energy sensors.
- Added HACS installation and custom repository instructions.
