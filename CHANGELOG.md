# Changelog

All notable changes to RevampKey will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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
- **0.1.0-beta** (2025-01-19) - Initial public beta release

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
