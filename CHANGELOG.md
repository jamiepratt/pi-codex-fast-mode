# Changelog

All notable changes to this project will be documented in this file. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and the project uses [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Added

- Fast-mode eligibility for the exact documented Codex IDs `gpt-6-astra`, `gpt-6-sol`, `gpt-6-luna`, and `gpt-6.1-sol`, scoped to `openai-codex`; undocumented GPT-6 variants remain inactive.
- Regression coverage for GPT-6 eligibility, provider exclusions, immutable Priority payloads, activation/status without pricing metadata, and unchanged preference semantics.

### Fixed

- Activation no longer treats missing credit estimates as ineligibility. Eligible GPT-6 models show active status and request `service_tier: "priority"`, with higher-usage messaging and no invented model-specific speed or credit multipliers.

### Documentation

- Cite the current OpenAI Codex speed/models pages and API Fast mode guide confirming `priority`/`fast` equivalence. Existing GPT-5 behavior, commands, persistence, and wire value are unchanged; this does not enable Ultrafast.

## [0.2.0] — 2026-07-30

### Changed

- Bare `/fast` now toggles and persists Fast mode; `/fast on`, `/fast off`, and `/fast status` remain available as explicit controls.

## [0.1.0] — 2026-07-29

### Added

- Correctness-first Codex Fast-mode request hook for GPT-5.4, GPT-5.5, and GPT-5.6 families.
- Explicit `/fast on | off | status` command and process-local `--fast` flag.
- Versioned, package-owned preference state with safe defaults, exclusive temporary files, atomic POSIX replacement, and a fail-safe Windows fallback.
- Eligible/inactive footer status and transparent speed, credit, conflict, and downgrade messaging.
- Strict TypeScript, Biome, Vitest coverage, Linux/Windows CI, production audit, and exact npm tarball allowlist checks.
- Public architecture, contribution, and security documentation.

### Security

- No runtime dependencies, provider replacement, independent network access, credential access, or request logging.
