# Changelog

All notable changes to **Windows Icon Refresher** will be documented in this file.

The project follows semantic-style versioning.

## [Unreleased]

### Planned

- Packaged `.exe` builds
- Additional diagnostics
- UI and DPI-scaling improvements
- More detailed repair result information

---

## [1.0] - 2026-08-15

### Added

- Initial public release
- **Quick Refresh** repair mode
- **Restart Explorer** repair mode
- **Deep Rebuild** repair mode
- Optional targeting of `.exe`, `.lnk`, and `.ico` files
- Windows shell icon refresh support
- Automatic Windows Explorer restart
- Current-user icon-cache database rebuild
- Icon-cache diagnostics
- Windows Explorer status display
- Activity log
- Modern dark Windows-inspired interface
- Local-only repair workflow
- No telemetry or data collection

### Notes

- Restart Explorer and Deep Rebuild can briefly make the taskbar and desktop disappear while `explorer.exe` restarts.
- Open File Explorer windows may close during those repair modes.
