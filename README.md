# 🪟 Windows Icon Refresher

<p align="center">
  <img src="https://i.imgur.com/kYIJKVL.png" alt="Windows Icon Refresher GUI for fixing blank taskbar icons, generic app icons, stale shortcuts, and corrupted Windows icon cache on Windows 11 and Windows 10" width="100%">
</p>

<p align="center">
  <strong>Fix blank, missing, generic, stale, or incorrect Windows taskbar and File Explorer icons in a few clicks.</strong>
</p>

<p align="center">
  A lightweight open-source Windows 11 / Windows 10 GUI that refreshes shell icons, restarts Windows Explorer, and rebuilds the current-user icon cache — without digging through Command Prompt repair steps.
</p>

<p align="center">
  <a href="https://github.com/alsvike/windows-icon-refresher/releases/tag/v1.0"><img alt="Version 1.0" src="https://img.shields.io/badge/version-1.0-4CC2FF?style=for-the-badge"></a>
  <a href="#-quick-start"><img alt="Windows 10 and Windows 11" src="https://img.shields.io/badge/Windows-10%20%7C%2011-0078D4?style=for-the-badge&logo=windows11&logoColor=white"></a>
  <a href="https://www.python.org/downloads/"><img alt="Python 3" src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white"></a>
  <a href="LICENSE.md"><img alt="MIT License" src="https://img.shields.io/badge/License-MIT-2EA44F?style=for-the-badge"></a>
</p>

<p align="center">
  <a href="#-what-it-fixes">What it fixes</a> •
  <a href="#-repair-modes">Repair modes</a> •
  <a href="#-quick-start">Quick start</a> •
  <a href="#-how-to-fix-blank-taskbar-icons-in-windows-11">Windows 11 fix</a> •
  <a href="#-troubleshooting">Troubleshooting</a> •
  <a href="ROADMAP.md">Roadmap</a> •
  <a href="#-faq">FAQ</a>
</p>

---

## ✨ What It Fixes

**Windows Icon Refresher 1.0** is built for common Windows icon-cache and shell problems such as:

- **Blank taskbar icons in Windows 11**
- **App icons not appearing on the Windows taskbar**
- **Generic app icons instead of the correct program icon**
- **White or blank shortcut icons** on the desktop, Start menu, or taskbar
- **Pinned taskbar icons showing the wrong icon after an app update**
- **Stale application icons that refuse to refresh**
- **File Explorer showing the wrong app or shortcut icon**
- **Windows 10 or Windows 11 icon cache corruption**
- **Shortcut icons remaining outdated after reinstalling an application**
- **Correct icon inside the `.exe`, but the wrong icon on the taskbar**

Instead of manually stopping Explorer, locating icon-cache database files, deleting them, and restarting the Windows shell, Windows Icon Refresher puts the whole repair workflow behind a simple desktop interface.

> **Current release:** `1.0`

---

## ⚡ Why Use Windows Icon Refresher?

Windows caches application, shortcut, taskbar, Start menu, and File Explorer icons so they load quickly. When those cached entries become stale or corrupted, Windows can keep showing an old, blank, generic, or incorrect icon even when the application itself is fine.

Windows Icon Refresher gives you a GUI for the most useful Windows icon repair actions:

- Refresh Windows shell icons and file associations
- Refresh a specific `.exe`, `.lnk`, or `.ico`
- Restart `explorer.exe`
- Clear current-user icon-cache database files
- Let Windows rebuild the icon cache automatically
- Watch repair progress in the Activity log

**Everything runs locally on your PC.** No telemetry, account, or cloud service is required for repair operations.

---

## 🛠 Repair Modes

| Mode | Best for | Explorer restart | Impact |
|---|---|---:|---|
| **Quick Refresh** | One stale or incorrect icon | No | Lowest |
| **Restart Explorer** | Most blank, generic, or missing taskbar icons | Yes | Recommended |
| **Deep Rebuild** | Corrupted or stubborn icon-cache problems | Yes | Strongest |

### 🔄 Quick Refresh

**Best for:** refreshing a stale Windows icon without restarting Explorer.

Quick Refresh sends Windows shell icon and file-association refresh notifications while keeping Windows Explorer running.

Use it when:

- One application icon suddenly looks wrong
- A shortcut icon has not refreshed
- You want the least disruptive repair

### 🧩 Restart Explorer

**Best for:** fixing most blank, generic, missing, or stale taskbar icons on Windows 11 and Windows 10.

This is the recommended first repair. Windows Icon Refresher refreshes the shell, restarts `explorer.exe`, then performs another icon refresh after Explorer starts again.

Use it when:

- A Windows taskbar icon is blank
- An app icon is not appearing correctly on the taskbar
- A pinned application shows a generic icon
- File Explorer displays an old application icon
- Quick Refresh did not solve the problem

> The taskbar and desktop may briefly disappear while Windows Explorer restarts.

### 🧹 Deep Rebuild

**Best for:** clearing and rebuilding a corrupted Windows icon cache when normal refreshes do not work.

Deep Rebuild stops Windows Explorer, removes the current user's icon-cache database files, starts Explorer again, and asks Windows to rebuild the icon cache.

Use it when:

- Windows 11 keeps showing generic taskbar icons
- Multiple application shortcuts show blank icons
- Restart Explorer does not repair the icon
- The Windows icon cache appears corrupted
- An old pinned icon keeps returning after an application update

> **Warning:** Open File Explorer windows may close while Explorer is restarted.

---

## 🚀 Quick Start

### Requirements

- Windows 11 or Windows 10
- Python 3
- `ttkbootstrap`

### 1. Clone the repository

```powershell
git clone https://github.com/alsvike/windows-icon-refresher.git
cd windows-icon-refresher
```

### 2. Install dependencies

```powershell
py -m pip install -r requirements.txt
```

### 3. Run Windows Icon Refresher

```powershell
py windows_icon_refresher.py
```

### Prefer a ZIP?

1. Select **Code** on this repository.
2. Choose **Download ZIP**.
3. Extract the archive.
4. Open PowerShell in the extracted folder.
5. Install dependencies.
6. Run `windows_icon_refresher.py`.

---

## 🧭 How to Fix Blank Taskbar Icons in Windows 11

For most Windows 11 taskbar icon problems:

1. Open **Windows Icon Refresher**.
2. Keep **Restart Explorer** selected.
3. Optionally click **Browse** and select the affected application's `.exe`, `.lnk`, or `.ico`.
4. Click **Fix taskbar icon**.
5. Wait for Windows Explorer to restart.
6. Check the affected taskbar icon.
7. If it is still wrong, run **Deep Rebuild**.
8. If a pinned icon remains stale, unpin the app, launch it again, and repin it after the repair.

For a detailed walkthrough, see **[Fix Blank Taskbar Icons in Windows 11](docs/FIX-BLANK-TASKBAR-ICONS-WINDOWS-11.md)**.

---

## 🎯 Fix One Specific Application Icon

If only one program has the wrong taskbar or shortcut icon, select its executable or shortcut before running the repair.

Supported target types:

| File type | Purpose |
|---|---|
| `.exe` | Application executable |
| `.lnk` | Windows shortcut |
| `.ico` | Icon file |

Leave the target field empty to perform a global Windows icon refresh.

---

## ♻️ How to Rebuild the Windows Icon Cache

If restarting Explorer does not fix your icons, **Deep Rebuild** automates the current-user icon-cache rebuild process.

It:

1. Stops Windows Explorer.
2. Locates the current user's Windows icon-cache database files.
3. Removes those cache files.
4. Starts Windows Explorer again.
5. Requests a final shell icon refresh.
6. Allows Windows to recreate the icon cache as needed.

See **[How to Rebuild the Windows Icon Cache on Windows 11 and Windows 10](docs/REBUILD-WINDOWS-ICON-CACHE.md)** for the full guide.

---

## 🧰 Troubleshooting

### Windows 11 taskbar icons are blank

Start with **Restart Explorer**. If the blank taskbar icon remains, select the affected application's `.exe` or `.lnk` and run the repair again. Use **Deep Rebuild** for persistent icon-cache problems.

### Taskbar icons show generic app icons

Generic application icons can be caused by stale cache entries or shortcut problems. Run **Restart Explorer** first, then **Deep Rebuild** if the correct program icon does not return.

### App icons are not appearing on the taskbar

If the application is open but its expected icon is missing or replaced by a generic placeholder, target the application's executable and run **Restart Explorer**. A cache rebuild may be required if several apps are affected.

### Pinned taskbar icon is not updating after an app update

Unpin the app, run **Restart Explorer** or **Deep Rebuild**, launch the updated application, and pin it again.

### File Explorer shows the wrong application icon

Select the affected executable or shortcut and run **Restart Explorer**. If File Explorer continues to display a stale icon, use **Deep Rebuild**.

### Desktop or Start menu shortcuts show blank icons

A stale icon cache can affect shortcuts outside the taskbar too. Try **Restart Explorer**, followed by **Deep Rebuild** if the blank shortcut icons remain.

➡️ See the full **[Troubleshooting Guide](docs/TROUBLESHOOTING.md)**.

---

## 🔒 Privacy & Safety

Windows Icon Refresher is designed to run locally.

It does **not**:

- Collect personal information
- Send analytics or telemetry
- Track usage
- Upload selected file paths
- Require an account
- Require a cloud service to repair icons

Depending on the selected repair mode, the program can:

- Send Windows shell icon refresh notifications
- Refresh Windows icon and file associations
- Notify Windows that a selected application or shortcut changed
- Restart `explorer.exe`
- Remove current-user icon-cache database files
- Allow Windows to recreate the icon cache

It does **not** modify the selected application's executable.

### Explorer restart warning

**Quick Refresh** does not restart Explorer.

**Restart Explorer** and **Deep Rebuild** temporarily restart the Windows shell. During the repair:

- The Windows taskbar may disappear briefly
- Desktop icons may disappear briefly
- Open File Explorer windows may close

Windows Icon Refresher attempts to start Explorer again automatically after the repair.

Administrator privileges are normally not required because Deep Rebuild targets the current user's icon cache.

---

## ❓ FAQ

### How do I fix blank taskbar icons in Windows 11?

Open Windows Icon Refresher and run **Restart Explorer**. If the blank taskbar icon remains, select the affected application's executable or shortcut and run the repair again. Use **Deep Rebuild** for stubborn cache corruption.

### How do I rebuild the icon cache in Windows 11?

Choose **Deep Rebuild**. Windows Icon Refresher stops Explorer, clears current-user icon-cache database files, starts Explorer again, and lets Windows rebuild the icon cache.

### How do I refresh the Windows icon cache without restarting my PC?

Try **Quick Refresh** first. If a full shell reload is needed, **Restart Explorer** restarts `explorer.exe` without requiring a full Windows reboot.

### Why are my Windows 11 taskbar icons showing generic icons?

Generic taskbar icons can appear when Windows has stale or corrupted icon-cache data, when a shortcut is damaged, or when an application is supplying an unexpected icon. Start with **Restart Explorer** and use **Deep Rebuild** if the issue persists.

### How do I fix a wrong taskbar icon after updating an app?

Select the updated application's `.exe` or `.lnk`, run **Restart Explorer**, and repin the app if the old icon remains. Use **Deep Rebuild** for persistent stale cache entries.

### Can it fix File Explorer showing the wrong app icon?

Yes, when the problem is caused by stale Windows shell or icon-cache data. Target the affected executable or shortcut and run **Restart Explorer**, then use **Deep Rebuild** if necessary.

### Does Windows Icon Refresher delete my files?

It does not delete personal documents or modify application executables. Deep Rebuild removes current-user Windows icon-cache database files so Windows can recreate them.

### Does it need administrator rights?

Normally no. The utility is designed around the current user's Windows icon cache and shell process.

### Does it work on Windows 10?

Yes. Windows Icon Refresher is intended for both Windows 11 and Windows 10.

---

## 📚 Guides

- 🪟 **[Fix Blank Taskbar Icons in Windows 11](docs/FIX-BLANK-TASKBAR-ICONS-WINDOWS-11.md)**
- ♻️ **[Rebuild the Windows Icon Cache on Windows 11 and Windows 10](docs/REBUILD-WINDOWS-ICON-CACHE.md)**
- 🧰 **[Troubleshooting Windows Icon Refresher](docs/TROUBLESHOOTING.md)**
- 🗺 **[Planned Features & Development Roadmap](ROADMAP.md)**

---

## 🗂 Project Structure

```text
windows-icon-refresher/
├── windows_icon_refresher.py
├── requirements.txt
├── README.md
├── ROADMAP.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── CODE_OF_CONDUCT.md
├── LICENSE.md
└── docs/
    ├── FIX-BLANK-TASKBAR-ICONS-WINDOWS-11.md
    ├── REBUILD-WINDOWS-ICON-CACHE.md
    └── TROUBLESHOOTING.md
```

---

## 👨‍💻 Development

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

## 🗺 Roadmap

The roadmap is organized by priority, from **P0 — Next** through **P3 — Future / Exploratory**, with planned work covering smarter diagnostics, one-click repair, shortcut inspection, packaging, accessibility, automation, and deeper Windows shell tooling.

➡️ **[View the full Windows Icon Refresher roadmap](ROADMAP.md)**

Feature suggestions are welcome through GitHub Issues.

---

## 🤝 Contributing

Bug reports, feature requests, UI improvements, documentation improvements, and code contributions are welcome.

Please read:

- [`CONTRIBUTING.md`](CONTRIBUTING.md)
- [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)

---

## 🛡 Security

Please do not publish suspected security vulnerabilities in public GitHub Issues.

See [`SECURITY.md`](SECURITY.md).

---

## 📜 License

Released under the **MIT License**.

See [`LICENSE.md`](LICENSE.md).

---

## ℹ️ Disclaimer

Windows Icon Refresher is an independent open-source utility and is not affiliated with, endorsed by, or sponsored by Microsoft.

Windows and File Explorer are trademarks of Microsoft Corporation.

---

<p align="center">
  <strong>🪟 Windows Icon Refresher 1.0</strong><br>
  Fix blank taskbar icons, generic app icons, stale shortcuts, and corrupted Windows icon-cache problems from one simple GUI.
</p>

<p align="center">
  If the project helped you, consider giving the repository a ⭐.
</p>
