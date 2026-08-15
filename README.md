# Windows Icon Refresher

<p align="center">
  <img src="https://i.imgur.com/kYIJKVL.png" alt="Windows Icon Refresher" width="100%">
</p>

<p align="center">
  <strong>A lightweight Windows utility for fixing stale, blank, generic, or incorrect taskbar and File Explorer icons.</strong>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#repair-modes">Repair Modes</a> •
  <a href="#installation">Installation</a> •
  <a href="#how-to-use">How to Use</a> •
  <a href="#troubleshooting">Troubleshooting</a> •
  <a href="#privacy">Privacy</a>
</p>

---

## About

**Windows Icon Refresher** is a simple Windows 10/11 desktop utility designed to repair icon-cache problems that can cause applications, shortcuts, taskbar items, or File Explorer entries to display the wrong icon.

Common symptoms include:

- Blank taskbar icons
- Generic white-file icons
- Old or stale application icons
- Incorrect icons after an application update
- Shortcut icons that do not refresh
- File Explorer showing an outdated icon
- A pinned taskbar app continuing to use an old icon

Windows Icon Refresher provides three repair levels so you can start with the least disruptive option and only use a full icon-cache rebuild when necessary.

> **Current version:** `1.0`

---

## Features

- **Quick Refresh** for a low-impact Windows shell icon refresh
- **Restart Explorer** for the recommended repair method
- **Deep Rebuild** for stubborn icon-cache problems
- Optionally target a specific `.exe`, `.lnk`, or `.ico`
- Refresh the Windows shell without manually using Command Prompt
- Restart Windows Explorer automatically
- Rebuild the current user's Windows icon cache
- Live activity logging
- Current icon-cache diagnostics
- Windows Explorer status display
- Modern dark Windows-inspired interface
- No account required
- No telemetry
- No data collection
- No internet connection required for repair operations

---

## Repair Modes

### Quick Refresh

The least disruptive option.

Quick Refresh asks Windows to redraw shell icons and refresh icon associations without restarting Windows Explorer.

**Use this when:**

- One icon suddenly looks wrong
- You want the fastest possible repair
- You do not want Explorer to restart

---

### Restart Explorer

The recommended first repair for most icon problems.

This mode refreshes the Windows shell, restarts `explorer.exe`, and then requests another icon refresh.

**Use this when:**

- Quick Refresh did not fix the icon
- A taskbar icon remains stale
- File Explorer is showing an old application icon
- You want the recommended repair method

> The taskbar and desktop can briefly disappear while Windows Explorer restarts.

---

### Deep Rebuild

The strongest repair option.

Deep Rebuild stops Windows Explorer, removes the current user's icon-cache database files, restarts Explorer, and asks Windows to rebuild the cache.

**Use this when:**

- The icon remains wrong after restarting Explorer
- Multiple application icons are broken
- The icon cache appears corrupted
- Windows repeatedly shows generic or blank icons

> **Warning:** Open File Explorer windows may close while Explorer is restarted.

---

## Requirements

- Windows 10 or Windows 11
- Python 3.10 or newer recommended
- `ttkbootstrap`

Install the required Python package with:

```powershell
py -m pip install ttkbootstrap
```

---

## Installation

### Option 1 — Run from source

Clone the repository:

```powershell
git clone https://github.com/YOUR_USERNAME/windows-icon-refresher.git
cd windows-icon-refresher
```

Install dependencies:

```powershell
py -m pip install -r requirements.txt
```

Run the application:

```powershell
py windows_icon_refresher.py
```

---

### Option 2 — Download the repository

1. Open the repository on GitHub.
2. Select **Code**.
3. Choose **Download ZIP**.
4. Extract the ZIP.
5. Install the dependency:

```powershell
py -m pip install ttkbootstrap
```

6. Run:

```powershell
py windows_icon_refresher.py
```

---

## How to Use

### 1. Choose a repair mode

Start with **Restart Explorer** for most problems.

If you only want a low-impact refresh, choose **Quick Refresh**.

If the icon is still broken after restarting Explorer, use **Deep Rebuild**.

### 2. Optionally select the affected application

If only one application has the wrong icon, use **Browse** and select its:

- `.exe`
- `.lnk`
- `.ico`

You can leave this field empty to perform a global icon refresh.

### 3. Start the repair

Click the repair button shown for the selected mode.

The Activity section will show what the utility is doing.

### 4. Check the result

After the repair completes, check the taskbar or File Explorer.

If a pinned taskbar icon is still wrong, unpin and repin the application after performing a Deep Rebuild.

---

## What the Program Changes

Windows Icon Refresher only performs actions related to the current Windows shell and current-user icon cache.

Depending on the selected repair mode, it can:

- Send Windows shell icon refresh notifications
- Refresh Windows icon associations
- Restart `explorer.exe`
- Remove current-user icon-cache database files
- Allow Windows to rebuild the icon cache

It does **not** modify the selected application's executable.

---

## Privacy

Windows Icon Refresher is designed to run locally.

It does not:

- Collect personal information
- Send analytics
- Track usage
- Upload selected file paths
- Require an account
- Require a cloud service for repair operations

The repair process uses Windows features available on the local computer.

---

## Safety

The **Quick Refresh** mode does not restart Explorer.

The **Restart Explorer** and **Deep Rebuild** modes temporarily restart Windows Explorer. During that process:

- The taskbar may disappear briefly
- Desktop icons may disappear briefly
- Open File Explorer windows may close

Explorer is automatically started again after the repair.

Administrator privileges are normally not required because the Deep Rebuild process targets the current user's icon cache.

---

## Troubleshooting

### The icon is still wrong after Quick Refresh

Try **Restart Explorer**.

### The icon is still wrong after Restart Explorer

Select the affected application's `.exe` or `.lnk` and run the repair again.

If that does not work, use **Deep Rebuild**.

### Deep Rebuild finished but one app still has the wrong icon

The application or shortcut may itself be supplying an incorrect icon.

Try:

1. Unpinning the application from the taskbar.
2. Closing the application.
3. Running Deep Rebuild.
4. Launching the application again.
5. Pinning it to the taskbar again.

### The taskbar disappears

This is expected while Windows Explorer is restarting.

It should return automatically after a few seconds.

### File Explorer windows closed

Restarting `explorer.exe` can close open File Explorer windows. This is expected behavior for the Restart Explorer and Deep Rebuild modes.

More troubleshooting information is available in [`docs/TROUBLESHOOTING.md`](docs/TROUBLESHOOTING.md).

---

## Project Structure

```text
windows-icon-refresher/
├── windows_icon_refresher.py
├── requirements.txt
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── SUPPORT.md
├── CODE_OF_CONDUCT.md
├── LICENSE.md
├── docs/
│   ├── HOW_IT_WORKS.md
│   └── TROUBLESHOOTING.md
└── .github/
    ├── ISSUE_TEMPLATE/
    │   ├── bug_report.md
    │   └── feature_request.md
    └── PULL_REQUEST_TEMPLATE.md
```

---

## Development

Install the development dependency:

```powershell
py -m pip install ttkbootstrap
```

Run the application directly:

```powershell
py windows_icon_refresher.py
```

When contributing, please test changes on Windows before opening a pull request.

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for contribution guidelines.

---

## Versioning

The project uses semantic-style version numbers.

The current public release is:

```text
1.0
```

See [`CHANGELOG.md`](CHANGELOG.md) for release history.

---

## Roadmap

Possible future improvements include:

- Packaged `.exe` releases
- Light theme
- Automatic Windows theme detection
- Improved diagnostics
- Optional icon-cache backup
- Better DPI scaling
- Additional Windows shell repair tools
- More detailed repair results
- Localization

Suggestions are welcome through GitHub Issues.

---

## Contributing

Contributions, bug reports, documentation improvements, and feature suggestions are welcome.

Before contributing, please read:

- [`CONTRIBUTING.md`](CONTRIBUTING.md)
- [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)

---

## Reporting Bugs

When reporting a bug, please include:

- Windows version
- Python version
- Windows Icon Refresher version
- Repair mode used
- What icon was affected
- What you expected to happen
- What actually happened
- Any traceback or Activity log output

Use the repository's **Bug Report** issue template when possible.

---

## Security

Please do not publish security vulnerabilities as public GitHub Issues.

See [`SECURITY.md`](SECURITY.md) for the recommended reporting process.

---

## License

Released under the MIT License.

See [`LICENSE.md`](LICENSE.md).

---

## Disclaimer

Windows Icon Refresher is an independent open-source utility and is not affiliated with, endorsed by, or sponsored by Microsoft.

Windows and File Explorer are trademarks of Microsoft Corporation.

Use the software at your own discretion. Although the application is designed to use standard Windows shell operations, restarting Explorer can close open File Explorer windows.

---

## Support the Project

If Windows Icon Refresher helped you, you can support the project by:

- Starring the repository
- Reporting bugs
- Suggesting improvements
- Contributing code or documentation
- Sharing the project with other Windows users

---

<p align="center">
  <strong>Windows Icon Refresher 1.0</strong><br>
  Fix stale Windows icons without digging through command-line repair steps.
</p>
