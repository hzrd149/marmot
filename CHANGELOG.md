# Changelog

<!-- All notable changes to this project will be documented in this file. -->

<!-- The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), -->
<!-- and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html). -->

<!-- Template

## Unreleased

### Breaking changes

### Changed

### Added

### Fixed

### Removed

### Deprecated

-->

## Unreleased

### Breaking changes

### Changed

- **Encoding format migration**: KeyPackage (kind:443) and Welcome (kind:444) events are transitioning from hex to base64 encoding for the `content` field. The encoding format is specified by the `encoding` tag:
  - `["encoding", "base64"]` - Content is base64-encoded (~33% smaller, **required for new implementations**)
  - `["encoding", "hex"]` or tag absent - Content is hex-encoded (**deprecated**, supported for backward compatibility only)

  Implementations MUST support reading both formats during the transition period. New implementations MUST use base64 encoding. Hex encoding will be removed in a future version.

### Added

### Fixed

### Removed

### Deprecated
