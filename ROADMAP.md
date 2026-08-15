# 🗺 Windows Icon Refresher Roadmap

This roadmap describes possible future directions for **Windows Icon Refresher**. Priorities reflect the current product direction and may change as bugs, Windows behavior, user feedback, and contributor interest evolve.

> A roadmap item is a plan or idea, not a release promise.

## Priority Legend

| Priority | Meaning |
|---|---|
| **P0 — Next** | Highest-value work that would most improve reliability, ease of use, or distribution |
| **P1 — High** | Strong candidates after the core P0 work is stable |
| **P2 — Medium** | Useful improvements that broaden the product or polish the experience |
| **P3 — Future / Exploratory** | Larger, more experimental, or lower-urgency ideas |

---

## 🔥 P0 — Next

### 1. Smart Diagnosis
Automatically inspect Explorer state, icon-cache health, selected targets, shortcuts, and icon sources, then suggest the most likely cause of the problem.

**Goal:** tell the user *what is probably wrong* before asking them to choose a repair mode.

### 2. Smart Repair
Add a one-click repair flow that begins with the least disruptive fix and escalates only when necessary.

**Possible flow:** Quick Refresh → Restart Explorer → Deep Rebuild.

### 3. Pinned Taskbar App Scanner
Detect pinned taskbar shortcuts and present them in the UI so users can choose a broken app without manually browsing for an `.exe` or `.lnk`.

### 4. Shortcut Inspector
Inspect `.lnk` files and show their target path, icon path, working directory, and whether each referenced file still exists.

### 5. Icon Preview & Source Comparison
Preview the icon embedded in an executable, shortcut, or `.ico` file and compare it with the icon source configured by the shortcut.

### 6. Post-Repair Verification
After a repair, automatically re-check Explorer, cache files, target paths, and relevant shell state instead of reporting success solely because the repair commands completed.

### 7. Diagnostic Report Export
Export a privacy-conscious report containing Windows version, app version, Explorer status, cache statistics, selected repair mode, repair result, and relevant log entries.

### 8. Copy Report for GitHub Issue
Generate a Markdown-formatted support report that users can paste directly into a GitHub bug report.

### 9. Explorer Recovery Watchdog
Strengthen Explorer recovery with timed health checks, automatic retries, and a visible recovery action if `explorer.exe` does not return after a repair.

### 10. Icon-Cache Backup & Restore
Optionally back up current-user icon-cache database files before Deep Rebuild and provide a controlled restore workflow.

### 11. Standalone Windows `.exe`
Publish a self-contained executable so normal users do not need Python or `ttkbootstrap` installed.

### 12. Automated Build & Release Pipeline
Use GitHub Actions to build release artifacts, run checks, and attach versioned Windows packages to GitHub Releases.

---

## 🚀 P1 — High

### 13. Batch Repair
Allow users to select multiple applications or shortcuts and refresh them in one repair session.

### 14. Broken Shortcut Detection
Scan selected shortcuts for missing targets, missing custom icon files, invalid paths, and stale references.

### 15. Desktop & Start Menu Shortcut Scanner
Scan common current-user shortcut locations for broken or suspicious icon references.

### 16. Cache Health Score
Convert raw cache information into a simple health assessment such as **Healthy**, **Attention**, or **Likely Corrupted**, with an explanation of what triggered the result.

### 17. Repair History
Store a local history of repairs, including date, selected target, repair mode, duration, and result.

### 18. Detailed Step Progress
Replace a generic progress percentage with named stages such as **Inspecting**, **Stopping Explorer**, **Clearing Cache**, **Starting Explorer**, **Refreshing Shell**, and **Verifying**.

### 19. Drag-and-Drop Target Selection
Allow users to drag an `.exe`, `.lnk`, or `.ico` directly into the application window.

### 20. Command-Line Interface
Add a CLI for advanced users and scripts while keeping the graphical application as the primary interface.

**Example ideas:** `--quick`, `--restart-explorer`, `--deep`, `--target`, and `--report`.

### 21. Crash-Safe Repair State
Persist enough temporary state during destructive repair stages to make recovery safer if the application unexpectedly closes while Explorer is stopped.

### 22. Portable Release
Offer a portable build that can run from a folder or USB drive without installation.

### 23. Installer Package
Provide a normal Windows installer with Start menu shortcuts, uninstall support, version metadata, and application icons.

### 24. Automatic Windows Theme Detection
Follow the user's Windows light/dark preference automatically.

### 25. High-DPI & Display Scaling Improvements
Improve layout and font behavior across 100%, 125%, 150%, 175%, 200% and mixed-DPI multi-monitor setups.

---

## ✨ P2 — Medium

### 26. File-Association Diagnostics
Detect whether a visible icon problem may be caused by a file-association configuration rather than the icon cache itself, without silently changing associations.

### 27. Icon Resource Inspector
Show available icon resources/indexes inside supported executables and DLLs when Windows exposes more than one icon resource.

### 28. Icon Extraction / Export
Allow users to extract an application's icon for troubleshooting or backup purposes.

### 29. Optional Thumbnail-Cache Repair
Provide a clearly separate tool for Windows thumbnail-cache problems so users can distinguish thumbnail issues from icon-cache issues.

### 30. Repair Dry Run
Preview what a repair intends to do — files involved, whether Explorer will restart, and which caches will be touched — before making changes.

### 31. Support Bundle
Create a ZIP containing sanitized diagnostic output, logs, and application metadata that users can attach to a GitHub Issue.

### 32. Automatic Update Checker
Optionally check GitHub Releases for newer versions and link users to the official release page. This should remain opt-in or clearly disclosed and should not add telemetry.

### 33. Keyboard Navigation & Accessibility Pass
Improve tab order, focus indicators, shortcuts, screen-reader labels, and contrast for users who navigate without a mouse.

### 34. Localization
Support translated interface strings and documentation for additional languages.

### 35. Light Theme & Accent Options
Add a polished light theme and optional accent customization while keeping the current dark interface as a first-class experience.

### 36. System Tray Quick Actions
Provide optional tray actions for Quick Refresh, opening diagnostics, or restoring Explorer when the main window is closed.

### 37. Shell Context-Menu Integration
Optionally add a Windows Explorer context-menu action such as **Refresh this app icon** for supported files or shortcuts.

### 38. Better Result Summaries
Show exactly what happened after repair: caches removed, retries performed, Explorer restart result, target refreshed, elapsed time, and verification status.

---

## 🧪 P3 — Future / Exploratory

### 39. `winget` Distribution
Explore publishing the utility through Windows Package Manager once release packaging and update practices are mature.

### 40. MSIX Packaging
Evaluate MSIX as an additional installation/distribution format if it fits the Explorer interaction requirements.

### 41. Code-Signed Releases
Sign production executables and installers when a sustainable signing process is available.

### 42. Multi-User Diagnostics
Explore detecting icon-cache problems across multiple Windows profiles when explicitly run with appropriate privileges.

### 43. JSON CLI Output
Provide structured diagnostic and repair results for scripts, automated support tooling, and power users.

### 44. Advanced Shell Diagnostics
Add deeper read-only checks for shell state and icon-related Windows configuration while keeping repair actions scoped and understandable.

### 45. Modular Repair Engine
Separate the repair engine, diagnostics, shortcut inspection, logging, and UI into reusable modules to make testing and contributions easier.

### 46. Automated Test Suite
Add unit tests for path handling, cache discovery, report generation, shortcut parsing, and repair decision logic, plus Windows-specific integration tests where practical.

### 47. Expanded CI Checks
Add linting, formatting, type checking, packaging tests, and smoke tests to reduce regressions before releases.

### 48. Community-Requested Repair Modules
Consider additional narrowly scoped Windows shell repair tools only when they clearly fit the project and can be implemented safely without turning the application into a generic system-cleaner utility.

---

## Product Principles

Future features should follow a few rules:

- **Diagnose before changing things.**
- **Start with the least disruptive repair.**
- **Keep destructive operations explicit.**
- **Prefer current-user changes over system-wide changes.**
- **Keep repair behavior understandable and reversible where possible.**
- **Do not add telemetry just to measure usage.**
- **Do not become a generic registry cleaner or "PC optimizer."**
- **Keep Windows icon, shortcut, Explorer, and shell repair as the core focus.**

---

## 💡 Suggest a Feature

Feature ideas and feedback are welcome through GitHub Issues.

When suggesting a feature, explain:

- What problem it solves
- Who would benefit
- What the ideal workflow looks like
- Whether it changes Windows state or is diagnostic-only
- Any screenshots or examples that help explain the problem
