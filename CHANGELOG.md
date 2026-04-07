# Changelog

All notable changes to RevampKey will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.3.1-beta] - 2026-04-07

### Fixed
- **RevampAI sidebar now loads every time** — Fixed an issue where the RevampAI panel would show a blank screen or fail silently on roughly 2 out of 3 cold starts. It now loads correctly and consistently on every launch.
- **Model picker remembers your selection** — The AI model dropdown was occasionally resetting to the first available model (about 2 in 10 reloads) instead of showing the one you last selected. Your choice is now preserved reliably across sessions.

## [0.3.0-beta] - 2026-04-07

### Added
- **RevampKey Dark theme** — A new built-in dark theme with a refined charcoal palette is now included and set as the default dark theme. No extra installation needed; it applies automatically on first launch.
- **Open Folder shortcut in sidebar** — When RevampKey is launched without a workspace, the sidebar now shows a direct "Open Folder" button so you can get started without hunting through the menus.

### Changed
- **Faster sign-in experience** — The login screen now appears instantly on first install or after signing out, instead of sitting through a loading animation before being redirected.
- **AI model display auto-syncs** — The selected AI model name in the toolbar now correctly reflects your account's available models right away, without requiring a manual re-selection after sign-in.
- **Cleaner editor UI** — Removed third-party AI assistant icons and suggestions from the title bar, command center, status bar, and Help menu to keep the interface focused and uncluttered.
- **Smoother extension installs** — Extension installation no longer shows signature verification dialogs, resulting in a faster and less noisy install flow.

### Fixed
- **Sign-in retry now works correctly** — Dismissing the browser sign-in window and clicking "Sign In" again now reliably reopens the browser. Previously, cancelling could leave the login flow in a stuck state.
- **Cold start "Open a folder" prompt** — Fixed an issue where launching RevampKey with no workspace open would show "Initializing Revamp AI…" indefinitely instead of the expected "Open a folder to get started" prompt.


## [v0.2.3-beta] - 2026-04-06

### Added
- Expanded observability in the integrated RevampKey Runtime with analytics sampling controls, richer message/repo telemetry, and version-aware request metadata.
- Added public observability documentation coverage for Loki logging and PostHog event flow to improve operational clarity.

### Changed
- Updated integrated runtime from `revampkey-runtime-v0.1.19` to `revampkey-runtime-v0.1.23`.
- Improved runtime traceability and analytics identity handling with stronger user/context propagation and extension/runtime build metadata alignment.
- Advanced bridge-level and model-request observability context so diagnostics are more actionable across extension and runtime boundaries.

### Fixed
- Applied cumulative runtime fixes from `v0.1.20` to `v0.1.23`, including cross-platform compatibility hardening and repo-map crash prevention for empty graph scenarios.

### Security
- Continued local-first and privacy-focused defaults with telemetry/analytics disabled by default unless explicitly configured.

### Runtime Stability Note
- **RevampKey Runtime is the main engine behind RevampKey.**
- This release carries cumulative runtime hardening and observability maturation through `v0.1.20` to `v0.1.23`, improving reliability, debuggability, and release confidence.

## [v0.2.2-beta] - 2026-03-30

### Added
- Introduced a smoother checkpoint revert experience in RevampAI so users can confidently roll conversations back and continue from a cleaner state.
- Expanded release quality coverage with new automated checks around complex chat/stream flows.

### Changed
- Updated the integrated RevampKey Runtime to `v0.1.20`, bringing broad quality and reliability improvements to day-to-day AI-assisted workflows.
- Refined chat readability by replacing aggressive message truncation with better word wrapping in question cards.
- Improved release packaging flow to make distribution output more consistent across builds.

### Fixed
- Improved streaming and checkpoint handling stability in RevampAI to reduce interrupted responses during longer interactions.
- Resolved edge-case save/order issues around checkpoint operations for more predictable conversation state.

### Removed
- 

---

## [0.2.1-beta] - 2026-03-26

### Added
- RevampKey Runtime evolution summary integrated into the product changelog to improve transparency around core engine maturity.
- Runtime capabilities added since `revampkey-runtime-v0.1.3` include:
  - Turn-based conversation summarization and improved tool result management.
  - File memory management/status tracking and stronger context-handling workflows.
  - Safety checks and cleanup for orphaned/incomplete tool results before API submission.
  - RevampKey Model Info API integration with local caching, diagnostics, and environment metadata merge support.
  - Multi-conversation plan architecture with shared tracker/spec resources and restoration/self-healing flows.
  - Context-management, error-recovery, and design-document prompt systems for more resilient operation.
  - Prompt compression analysis/utilities and repo map regeneration documentation.

### Changed
- Updated integrated runtime from `revampkey-runtime-v0.1.3` to `revampkey-runtime-v0.1.17`.
- Runtime and engine-level improvements delivered across `v0.1.4` to `v0.1.17`:
  - Prompt, cache, and context optimization to reduce token usage and improve responsiveness.
  - Improved model/provider handling, metadata processing, and API settings behavior.
  - Repo map generation, timeout behavior, and cache handling refinements.
  - Dependency and compatibility updates (including tree-sitter/litellm-related updates).
  - Logging, storage, and conversation lifecycle refinements for better reliability and traceability.

### Fixed
- Core runtime fixes delivered across the upgraded range include:
  - Removal/cleanup of orphaned and incomplete tool-result sequences to prevent malformed message flows.
  - Cache-key and cache-control reliability issues affecting consistency/performance.
  - Model/provider routing and metadata edge cases.
  - Repo map and signature-related reliability issues.
  - Tracker patch update behavior improvements to preserve existing task/module titles during partial updates.

### Removed
- Runtime cleanup and maintenance in the upgraded range removed obsolete/unused references and outdated documentation where applicable to keep the engine lean and maintainable.

### Security
- Continued local-first and privacy-focused operation with telemetry/analytics disabled by default.

### Runtime Stability Note
- **RevampKey Runtime is the main engine behind RevampKey.**
- This release includes cumulative runtime hardening from `v0.1.4` through `v0.1.17`, with focused work on resiliency, context integrity, cache stability, and tracker correctness.

## [0.2.0-beta] - 2025-01-20

### Added
- Initial beta release of RevampKey
- AI-powered code refactoring capabilities
- Modern code editor based on Visual Studio Code (v1.108.0)
- Open VSX extension marketplace integration
- Privacy-first architecture - all processing on local machine
- Cross-platform support (Windows (Coming Soon), macOS, Linux)
- Automatic update system with GitHub releases integration
- Custom branding and user interface
- RevampAI auxiliary bar with enhanced UI/UX
- Linux package support: `.deb`, `.rpm`, `.tar.gz`
- macOS: Universal binary (Intel + Apple Silicon)
- Support for x64, ARM64, and ARMv7 architectures

### Changed
- Updated to VSCode upstream version 1.108.0
- Enhanced webview activation logic for RevampAI
- Improved build configuration for all platforms
- Updated license and copyright information
- Privacy-focused documentation and URLs

### Security
- Disabled telemetry by default
- Removed analytics and tracking
- Local-first data processing


## [0.1.0-beta] - 2025-01-19

### Added
- Initial beta release of RevampKey
- AI-powered code refactoring capabilities
- Modern code editor based on Visual Studio Code (v1.108.0)
- Open VSX extension marketplace integration
- Privacy-first architecture - all processing on local machine
- Cross-platform support (Windows, macOS, Linux)
- Automatic update system with GitHub releases integration
- Custom branding and user interface
- RevampAI auxiliary bar with enhanced UI/UX

### Changed
- Updated to VSCode upstream version 1.108.0
- Enhanced webview activation logic for RevampAI
- Improved build configuration for all platforms
- Updated license and copyright information
- Privacy-focused documentation and URLs

### Technical
- Linux package support: `.deb`, `.rpm`, `.tar.gz`
- Windows installers: x64 and ARM64
- macOS: Universal binary (Intel + Apple Silicon)
- Support for x64, ARM64, and ARMv7 architectures

### Security
- Disabled telemetry by default
- Removed analytics and tracking
- Local-first data processing

## Version History

### Beta Releases
- **0.3.1-beta** (2026-04-07) - Startup reliability and model picker fix release.
- **0.3.0-beta** (2026-04-07) - Dark theme, UI polish, and stability improvements.
- **v0.2.2-beta** (2026-03-30) - Streaming/checkpoint stability and runtime upgrade release.
- **0.2.1-beta** (2026-03-26) - Runtime maturity and reliability expansion release.
- **0.2.0-beta** (2025-01-20) - Initial feature-complete beta milestone.
- **0.1.0-beta** (2025-01-19) - Initial public beta release.

---

## How to Update

### Automatic Updates (Recommended)
RevampKey will notify you when updates are available:
1. Click the notification or go to **Help > Check for Updates**
2. Download and install the update
3. Restart RevampKey

### Manual Updates
1. Visit the [Releases page](https://github.com/revampai/revampkey/releases)
2. Download the latest version for your platform
3. Install following the platform-specific instructions

### Linux Package Managers
```bash
# Debian/Ubuntu
sudo apt update
sudo apt upgrade revampkey

# Fedora/RHEL
sudo dnf upgrade revampkey
```

---

## Reporting Issues

Found a bug or have a feature request? Please report it on our [GitHub Issues](https://github.com/revampai/revampkey/issues) page.

---

## Links
- **Website**: [revampkey.com](https://revampkey.com)
- **GitHub**: [github.com/revampai/revampkey](https://github.com/revampai/revampkey)
- **Releases**: [github.com/revampai/revampkey/releases](https://github.com/revampai/revampkey/releases)
