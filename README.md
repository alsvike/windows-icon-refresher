# Windows Icon Refresher

<p align="center">
  <img src="https://i.imgur.com/kYIJKVL.png" alt="Windows Icon Refresher - fix broken, blank, stale, or generic taskbar icons on Windows 10 and Windows 11" width="100%">
</p>

<p align="center">
  <strong>Fix broken, blank, stale, generic, or incorrect taskbar and File Explorer icons on Windows 10 and Windows 11.</strong>
</p>

<p align="center">
  A lightweight Python desktop utility that refreshes the Windows icon cache, restarts Windows Explorer, and rebuilds corrupted icon-cache files without requiring manual Command Prompt repair steps.
</p>

<p align="center">
  <a href="#fix-broken-windows-taskbar-icons">What it fixes</a> •
  <a href="#repair-modes">Repair modes</a> •
  <a href="#installation">Installation</a> •
  <a href="#how-to-fix-a-broken-taskbar-icon">How to use</a> •
  <a href="#windows-icon-cache-troubleshooting">Troubleshooting</a>
</p>

---

## Fix Broken Windows Taskbar Icons

**Windows Icon Refresher** is an open-source Windows 10 and Windows 11 icon repair utility for users experiencing broken taskbar icons, blank application icons, generic white-file icons, stale shortcut icons, or incorrect File Explorer icons.

It is designed for common Windows icon-cache problems such as:

- Windows 11 taskbar icon is blank or missing
- Windows 10 taskbar icon shows the wrong application icon
- Pinned taskbar app keeps showing an old icon after an update
- File Explorer displays a generic white icon instead of the app icon
- Desktop or Start menu shortcut icon does not refresh
- Application icon is correct in the `.exe` but wrong on the taskbar
- Windows icon cache appears corrupted
- A shortcut still shows an old icon after reinstalling or updating an app
- Taskbar icon remains stale after restarting the application

Instead of manually deleting icon-cache databases or entering shell commands, Windows Icon Refresher provides a graphical interface with three levels of repair.

> **Current version:** `1.0`

---

## Why Use Windows Icon Refresher?

Windows stores application and shell icons in cache files so it can display them quickly. Sometimes that cache becomes stale or corrupted, causing Windows to keep showing an old, blank, generic, or incorrect icon.

Windows Icon Refresher gives you a simple GUI for the most common Windows icon cache repair steps:

- Refresh Windows shell icon associations
- Refresh a specific `.exe`, `.lnk`, or `.ico`
- Restart `explorer.exe`
- Rebuild the current-user Windows icon cache
- Let Windows recreate icon-cache database files automatically

The repair operations run locally on your PC.

---

## Features

- **Fix blank Windows taskbar icons**
- **Fix generic white application icons**
- **Refresh stale Windows 10 and Windows 11 icons**
- **Repair incorrect File Explorer icons**
- **Refresh pinned taskbar application icons**
- **Quick Refresh** for a low-impact Windows shell icon refresh
- **Restart Explorer** for the recommended taskbar icon repair
- **Deep Rebuild** for stubborn or corrupted Windows icon-cache problems
- Target a specific `.exe`, `.lnk`, or `.ico` file
- Restart Windows Explorer automatically
- Rebuild the current user's icon-cache database files
- Live repair progress and activity logging
- Icon-cache diagnostics
- Windows Explorer status display
- Modern dark Windows-inspired interface
- No telemetry or data collection
- No account required
- No internet connection required for icon repair operations

---

## Repair Modes

### Quick Refresh

**Best for:** quickly refreshing a stale Windows icon without restarting Explorer.

Quick Refresh sends Windows shell icon and file-association refresh notifications while keeping Windows Explorer running.

Try this when:

- One application icon suddenly looks wrong
- A shortcut icon has not refreshed
- You want to refresh Windows icons without restarting the taskbar

---

### Restart Explorer

**Best for:** fixing most broken, blank, or stale taskbar icons on Windows 10 and Windows 11.

This is the recommended first repair. Windows Icon Refresher refreshes the shell, restarts `explorer.exe`, and performs another icon refresh after Explorer starts again.

Try this when:

- A Windows taskbar icon is blank
- A pinned application shows the wrong icon
- File Explorer displays an old application icon
- Quick Refresh did not solve the problem

> The taskbar and desktop may briefly disappear while Windows Explorer restarts.

---

### Deep Rebuild

**Best for:** repairing a corrupted Windows icon cache when normal refreshes do not work.

Deep Rebuild stops Windows Explorer, removes the current user's icon-cache database files, starts Explorer again, and asks Windows to rebuild the icon cache.

Try this when:

- Windows 11 keeps showing generic taskbar icons
- Multiple application icons are blank or incorrect
- Restart Explorer does not repair the icon
- The Windows icon cache appears corrupted
- An old icon keeps returning after an application update

> **Warning:** Open File Explorer windows may close while Explorer is restarted.

---

## Requirements

- Windows 10 or Windows 11
- Python 3
- `ttkbootstrap`

Install the required package with:

```powershell
py -m pip install ttkbootstrap
```

---

## Installation

### Clone from GitHub

```powershell
git clone https://github.com/alsvike/windows-icon-refresher.git
cd windows-icon-refresher
```

Install dependencies:

```powershell
py -m pip install -r requirements.txt
```

Run Windows Icon Refresher:

```powershell
py windows_icon_refresher.py
```

### Download as ZIP

1. Select **Code** on this GitHub repository.
2. Choose **Download ZIP**.
3. Extract the archive.
4. Open PowerShell in the extracted folder.
5. Install the dependency:

```powershell
py -m pip install ttkbootstrap
```

6. Run:

```powershell
py windows_icon_refresher.py
```

---

## How to Fix a Broken Taskbar Icon

For most Windows taskbar icon problems:

1. Open **Windows Icon Refresher**.
2. Leave **Restart Explorer** selected.
3. Optionally select the affected application's `.exe`, `.lnk`, or `.ico` using **Browse**.
4. Click **Fix taskbar icon**.
5. Wait for Windows Explorer to restart.
6. Check the affected taskbar or File Explorer icon.
7. If the icon is still wrong, run **Deep Rebuild**.
8. For a stubborn pinned icon, unpin the application and pin it again after the repair.

### Fix One Specific Application Icon

If only one program has a broken icon, select its executable or shortcut before running the repair.

Supported target types:

- `.exe` — application executable
- `.lnk` — Windows shortcut
- `.ico` — icon file

You can leave the target field empty to perform a global Windows icon refresh.

---

## Windows Icon Cache Troubleshooting

### Windows 11 taskbar icon is blank

Run **Restart Explorer** first. If the blank taskbar icon remains, select the affected application's `.exe` or `.lnk` and run the repair again. Use **Deep Rebuild** if necessary.

### Windows taskbar shows a generic white icon

A generic white icon can indicate a stale icon cache, a damaged shortcut, or an application that is not exposing the expected icon. Run **Deep Rebuild**, then recreate or repin the shortcut if the problem persists.

### Pinned taskbar icon does not update after an app update

Unpin the app, run **Restart Explorer** or **Deep Rebuild**, launch the updated application, and pin it again.

### File Explorer shows the wrong icon

Select the affected executable or shortcut and run **Restart Explorer**. If File Explorer continues to show an old icon, use **Deep Rebuild**.

### Windows icon cache rebuild did not fix one application

The application or shortcut may itself be supplying an incorrect icon. Recreate the shortcut, verify it points to the correct executable, or reinstall/update the affected app.

For more detailed help, see [`docs/TROUBLESHOOTING.md`](docs/TROUBLESHOOTING.md).

---

## What the Program Changes

Depending on the repair mode, Windows Icon Refresher can:

- Send Windows shell icon refresh notifications
- Refresh Windows icon/file associations
- Notify Windows that a selected application or shortcut changed
- Restart `explorer.exe`
- Remove current-user icon-cache database files
- Allow Windows to recreate the icon cache

It does **not** modify the selected application's executable.

---

## Privacy

Windows Icon Refresher is designed to run locally.

It does not:

- Collect personal information
- Send analytics or telemetry
- Track usage
- Upload selected file paths
- Require an account
- Require a cloud service to repair icons

---

## Safety

**Quick Refresh** does not restart Explorer.

**Restart Explorer** and **Deep Rebuild** temporarily restart the Windows shell. During the repair:

- The Windows taskbar may disappear briefly
- Desktop icons may disappear briefly
- Open File Explorer windows may close

Windows Icon Refresher attempts to start Explorer again automatically after the repair.

Administrator privileges are normally not required because Deep Rebuild targets the current user's icon cache.

---

## Frequently Asked Questions

### How do I refresh the icon cache in Windows 11?

Use **Restart Explorer** for the recommended repair. If the icon cache appears corrupted or icons remain blank, use **Deep Rebuild** to remove the current-user cache files and let Windows recreate them.

### How do I fix a blank taskbar icon in Windows 11?

Open Windows Icon Refresher, choose **Restart Explorer**, optionally select the affected application's executable, and run the repair. If the icon remains blank, use **Deep Rebuild** and repin the application.

### How do I fix a wrong taskbar icon after updating an app?

Select the updated application's `.exe` or `.lnk`, run **Restart Explorer**, and repin the app if the old icon remains. Use **Deep Rebuild** for persistent stale cache entries.

### Does Windows Icon Refresher delete my files?

It does not delete personal documents or modify application executables. Deep Rebuild removes current-user Windows icon-cache database files so Windows can recreate them.

### Does it need administrator rights?

Normally no. The utility works with the current user's Windows icon cache and shell process.

### Does it work on Windows 10?

Yes. Windows Icon Refresher is intended for both Windows 10 and Windows 11.

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
├── CODE_OF_CONDUCT.md
├── LICENSE.md
└── docs/
    └── TROUBLESHOOTING.md
```

---

## Development

Install dependencies:

```powershell
py -m pip install -r requirements.txt
```

Run the application:

```powershell
py windows_icon_refresher.py
```

When contributing repair-logic changes, please test them on Windows before opening a pull request.

See [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

## Version

Current release:

```text
1.0
```

See [`CHANGELOG.md`](CHANGELOG.md) for release history.

---

## Roadmap

Possible future improvements include:

- Packaged Windows `.exe` releases
- Automatic Windows theme detection
- Light theme
- Improved DPI scaling
- More detailed Windows icon-cache diagnostics
- Optional icon-cache backup
- Additional shell repair tools
- Localization

Feature suggestions are welcome through GitHub Issues.

---

## Contributing

Bug reports, feature requests, UI improvements, documentation improvements, and code contributions are welcome.

Please read:

- [`CONTRIBUTING.md`](CONTRIBUTING.md)
- [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)

---

## Security

Please do not publish suspected security vulnerabilities in public GitHub Issues.

See [`SECURITY.md`](SECURITY.md).

---

## License

Released under the MIT License.

See [`LICENSE.md`](LICENSE.md).

---

## Disclaimer

Windows Icon Refresher is an independent open-source utility and is not affiliated with, endorsed by, or sponsored by Microsoft.

Windows and File Explorer are trademarks of Microsoft Corporation.

---

## Search Terms This Project Helps With

Windows Icon Refresher is intended for people searching for solutions to problems such as **fix blank taskbar icon Windows 11**, **refresh Windows icon cache**, **rebuild icon cache Windows 10**, **fix wrong taskbar icon after app update**, **generic white icon Windows 11**, **File Explorer wrong app icon**, **stale Windows shortcut icon**, **restart Explorer to refresh icons**, and **Windows taskbar icon cache repair tool**.

---

<p align="center">
  <strong>Windows Icon Refresher 1.0</strong><br>
  A simple GUI for repairing stale Windows taskbar, shortcut, and File Explorer icons.
</p>
