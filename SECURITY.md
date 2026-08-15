# Security Policy

## Supported Versions

Security fixes are currently provided for the latest public release of Windows Icon Refresher.

| Version | Supported |
| --- | --- |
| 1.0 | Yes |

## Reporting a Vulnerability

Please **do not** disclose suspected security vulnerabilities in a public GitHub Issue.

Instead, contact the repository owner privately through an appropriate contact method listed on their GitHub profile.

Please include as much of the following information as possible:

- A clear description of the vulnerability
- Steps to reproduce it
- The affected Windows Icon Refresher version
- Your Windows version
- The potential impact
- Relevant logs or screenshots
- Any suggested mitigation

Please allow reasonable time for investigation and remediation before public disclosure.

## Security Scope

Security reports are particularly useful when they involve:

- Unexpected file deletion
- File operations outside the intended current-user icon-cache locations
- Commands being executed outside the documented repair workflow
- Privilege escalation
- Unsafe path handling
- Arbitrary code execution
- Unexpected network activity
- Dependency-related vulnerabilities

## Project Security Design

Windows Icon Refresher is intended to operate locally and does not require a cloud service for icon repair operations.

The program is designed to limit destructive file operations to the current user's Windows icon-cache database files used by the Deep Rebuild repair mode.

Restart Explorer and Deep Rebuild intentionally interact with `explorer.exe`, so the taskbar, desktop, and File Explorer windows may temporarily disappear or close during normal operation.

## Public Bug Reports

General bugs that do not involve a security vulnerability can be reported through GitHub Issues.

Before posting logs or screenshots publicly, remove personal information, usernames, or sensitive file paths where appropriate.
