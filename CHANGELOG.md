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

- **Encoding format change**: KeyPackage (kind:443) and Welcome (kind:444) events now support tag-based dual-format encoding for the `content` field:
  - **Base64**: `["encoding", "base64"]` tag present, content is base64-encoded (preferred, ~33% smaller)
  - **Hex (default)**: No `encoding` tag or `["encoding", "hex"]`, content is hex-encoded (backward compatible)

  The tag-based approach eliminates ambiguity for strings like `deadbeef` that are valid in both hex and base64 but decode to different bytes. Implementations MUST support reading both formats. New implementations SHOULD use base64 encoding with the `["encoding", "base64"]` tag.

### Changed

### Added

### Fixed

### Removed

### Deprecated
