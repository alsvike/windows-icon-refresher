# Contributing to Windows Icon Refresher

Thanks for your interest in improving **Windows Icon Refresher**.

Contributions are welcome, including bug fixes, UI improvements, documentation changes, testing, and feature ideas.

## Before You Start

Please:

1. Check existing Issues before opening a duplicate.
2. Keep each pull request focused on one problem or feature.
3. Test functional changes on Windows.
4. Avoid unnecessary dependencies.
5. Preserve the project's local-only and privacy-friendly approach.

---

## Development Setup

Clone the repository:

```powershell
git clone https://github.com/alsvike/windows-icon-refresher.git
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

## Pull Requests

A good pull request should include:

- A clear title
- A short description of the problem
- A description of the solution
- Testing performed
- Screenshots for visible UI changes
- Any Windows compatibility concerns

Please avoid mixing unrelated changes into the same pull request.

---

## UI Contributions

When changing the interface:

- Keep the Windows-inspired dark visual language
- Maintain strong text contrast
- Avoid distracting or unnecessary animation
- Test on smaller displays
- Test common Windows DPI scaling levels when possible
- Keep all three repair modes easy to understand
- Make destructive or disruptive actions clear before execution

---

## Repair Logic Contributions

Changes to repair behavior should be tested carefully because the application interacts with Windows Explorer and the current-user icon cache.

Please describe:

- Which Windows version(s) were tested
- Which repair mode changed
- Which Windows shell behavior or API is being used
- How Explorer recovery behaves if the operation fails
- Whether current-user files are modified or deleted

Avoid expanding file-deletion behavior beyond the intended current-user icon-cache locations unless there is a strong, documented reason.

---

## Documentation Contributions

Documentation improvements are very welcome.

Please keep instructions understandable to users who are not familiar with Windows shell internals or command-line troubleshooting.

---

## Bug Reports

Useful bug reports should include:

- Windows version
- Windows Icon Refresher version
- Python version
- Repair mode used
- Whether a specific target file was selected
- Steps to reproduce the issue
- Relevant Activity log output
- Any traceback
- Screenshots when useful

Please remove sensitive information from logs and screenshots before posting them publicly.

---

## Feature Requests

When suggesting a feature, explain:

1. What problem it solves
2. Who would benefit
3. How you imagine it working
4. Any risks or tradeoffs you can think of

---

## Code Style

Keep the code readable and straightforward.

Prefer:

- Clear function and variable names
- Small, focused helpers
- Comments for Windows-specific behavior
- Defensive error handling around Explorer restart/cache operations
- Minimal dependency growth

---

## Version 1.0

The current public version is **1.0**. Changes intended for a future release should be documented in `CHANGELOG.md` under an **Unreleased** section.

---

## Code of Conduct

By participating in the project, you agree to follow [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md).
