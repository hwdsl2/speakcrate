# Changelog

Notable changes to SpeakCrate are documented here.

## 2026-10-24

Release: `2026.10.2`

### Fixed

- Fixed ARM64 CPU image startup by installing CPU-only PyTorch wheels.

## 2026-10-24

Release: `2026.10.1`

### Changed

- Established the first tagged source release. Docker images continue to update
  independently through existing moving tags.

## 2026-10-07

### Changed

- Rebranded as SpeakCrate (formerly `docker-kokoro`); the Docker image name
  remains `hwdsl2/kokoro-server`.

## 2026-07-09

### Added

- Added anonymous aggregate deployment/upgrade counts. Opt out with
  `KOKORO_DISABLE_USAGE_COUNTS=1`.

## 2026-06-25

### Fixed

- Fixed WAV output over server-sent events: the stream now contains one WAV
  header followed by PCM audio, rather than a separate WAV file per chunk.

## 2026-06-21

### Changed

- Added voice objects with an `id` field and more OpenAI voice aliases.
  Unknown voices now return an error instead of silently using the default.

### Fixed

- Corrected `pcm` output to signed 16-bit little-endian audio at 24 kHz mono,
  replacing the previous float32 output.

## 2026-06-20

### Added

- Added automatic API-key generation by default for fresh installs with
  persistent storage. Retrieve the key with `kokoro_manage --getkey`.
  Existing volumes without a key retain their previous authentication behavior.

## 2026-05-07

### Added

- Added OpenAI-compatible speech streaming over server-sent events.

## Earlier notable changes

- Added an OpenAI-compatible speech API with voice selection, speed and volume
  controls, and multiple audio formats.
- Added multilingual synthesis, audio streaming, persistent model caching,
  and NVIDIA CUDA images.
