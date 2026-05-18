# Changelog

All notable changes to this project will be documented here.
Format based on [Keep a Changelog](https://keepachangelog.com).

## [Unreleased]

## [2.1.0] - 2025-04-15

### Added

- New `/health` endpoint for monitoring
- Support for PostgreSQL 16

### Changed

- Default timeout increased from 5s to 10s

### Fixed

- Memory leak in connection pooling (#234)

### Deprecated

- `v1/users` endpoint — use `v2/users` instead

## [2.0.1] - 2025-02-20

### Fixed

- Critical security vulnerability in authentication module (CVE-2025-1234)
- Updated dependencies to address security issues
- Improved error handling in user registration flow

## [2.0.0] - 2025-01-10

### Breaking Changes

- Removed support for Node.js 16

[Unreleased]: https://github.com/user/repo/compare/v2.1.0...HEAD
[2.1.0]: https://github.com/user/repo/compare/v2.0.0...v2.1.0
