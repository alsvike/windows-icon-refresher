# Troubleshooting Windows Icon Refresher

This guide covers common issues with **Windows Icon Refresher 1.0** and the safest order to try repairs.

## Recommended Repair Order

For most icon problems, use the following order:

1. Run **Restart Explorer**.
2. Check the affected taskbar or File Explorer icon.
3. If the icon is still wrong, select the affected application's `.exe` or `.lnk` file and run **Restart Explorer** again.
4. If the problem remains, use **Deep Rebuild**.
5. If a pinned taskbar icon is still wrong, unpin the application, launch it again, and repin it.

---

## The Taskbar Icon Is Blank or Generic

A blank or generic white-file icon usually means Windows is displaying a stale cache entry, the shortcut is damaged, or the application is not exposing the expected icon.

Try **Restart Explorer** first. If that does not help:

1. Select the affected application's `.exe` or `.lnk` using **Browse**.
2. Run **Deep Rebuild**.
3. Unpin the application from the taskbar.
4. Launch the application normally.
5. Pin it to the taskbar again.

---

## The Old Icon Keeps Coming Back

If an old icon returns after a cache rebuild, the application or shortcut may itself be supplying that icon.

Try deleting and recreating the shortcut. For pinned taskbar applications, unpin and repin the application after running the repair.

---

## Quick Refresh Did Not Fix the Icon

This is not necessarily an error. **Quick Refresh** is intentionally the least disruptive mode.

Try **Restart Explorer** next. It refreshes the shell, restarts `explorer.exe`, and requests another icon refresh after Explorer starts again.

---

## Restart Explorer Did Not Fix the Icon

Select the affected application's `.exe`, `.lnk`, or `.ico` file and run the repair again.

If the problem remains, use **Deep Rebuild**.

---

## Deep Rebuild Could Not Delete Every Cache File

Some icon-cache database files may remain locked briefly.

Try the following:

1. Close unnecessary applications.
2. Run **Deep Rebuild** again.
3. If the problem continues, sign out of Windows and sign back in, then try again.

---

## The Taskbar or Desktop Disappeared

This is expected while Windows Explorer is restarting.

The taskbar, desktop icons, and File Explorer shell are hosted by `explorer.exe`. They should return automatically after a few seconds.

---

## Windows Explorer Did Not Return

Windows Icon Refresher attempts to start Explorer again automatically. If Explorer does not return:

1. Press `Ctrl + Shift + Esc` to open **Task Manager**.
2. Select **Run new task**.
3. Enter:

```text
explorer.exe
```

4. Select **OK**.

---

## Open File Explorer Windows Closed

This is expected when using **Restart Explorer** or **Deep Rebuild**. Restarting `explorer.exe` can close open File Explorer windows.

Save or finish important file operations before running those repair modes.

---

## `ttkbootstrap` Is Missing

If Python reports that `ttkbootstrap` cannot be imported, install it with:

```powershell
py -m pip install ttkbootstrap
```

Then run the application again.

---

## The Program Does Not Start

Confirm that Python is installed:

```powershell
py --version
```

Install the project requirements:

```powershell
py -m pip install -r requirements.txt
```

Then run:

```powershell
py windows_icon_refresher.py
```

If a traceback appears, include it when opening a GitHub Issue.

---

## The Program Works but One Specific App Is Still Wrong

This can happen when the problem is not the Windows icon cache itself.

Possible causes include:

- The application's executable contains the wrong icon.
- The shortcut points to an old executable.
- A pinned taskbar shortcut is stale.
- The application creates its own taskbar window icon at runtime.

Try recreating the shortcut or reinstalling/updating the affected application.

---

## Reporting a Bug

When opening an Issue, please include:

- Windows version
- Windows Icon Refresher version (`1.0`)
- Python version
- Repair mode used
- Whether you selected a specific `.exe`, `.lnk`, or `.ico`
- What you expected to happen
- What actually happened
- Relevant Activity log output
- Any Python traceback
- A screenshot when useful

Please remove any sensitive file paths or personal information before posting logs publicly.
