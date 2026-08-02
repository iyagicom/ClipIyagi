# ClipIyagi

A clipboard history manager that automatically saves copied content and lets you reuse it anytime.
Supports both Windows and Linux.

---

## Features

* **Automatic Saving** — Automatically records copied text and images
* **Global Hotkeys** — Instantly open the clipboard list from any application with a single shortcut
* **Auto Paste** — Selecting an item automatically pastes it into the previous active window
* **Number Shortcuts** — Instantly paste items using `1-9` and `0` keys without clicking
* **Pin Favorites** — Keep frequently used items at the top and exclude them from automatic cleanup
* **Item Editing** — Edit saved text before pasting
* **Tags / Search** — Add tags, filter with `#tagname`, and search instantly
* **Image Support** — Save images and preview them on hover
* **Dark Mode** — Switch between light and dark themes
* **System Tray** — Runs in the background and is always accessible from the tray icon

---

## Installation

### Windows

Install from the Microsoft Store or download the installer (`.exe`) from GitHub Releases.

### Linux (Ubuntu / Debian-based)

**Install using the `.deb` package (recommended)**

```bash
sudo dpkg -i clipiyagi_version_amd64.deb
```

**Additional setup for automatic paste**

ClipIyagi runs internally in X11 (XWayland) mode even on GNOME Wayland sessions.
Therefore, automatic paste works across desktop environments by installing only `xdotool`.

```bash
sudo apt install xdotool
```

> No `ydotool`, `wl-clipboard`, or uinput permission configuration is required.
> ClipIyagi is designed to always run through XWayland instead of native Wayland mode, allowing it to track the previous window and send paste keystrokes using only `xdotool`.
> No additional permissions or background daemon setup are needed.

---

## How to Use

1. After installation, launch ClipIyagi and its icon will appear in the system tray
2. Copy text or images normally — ClipIyagi automatically saves them
3. Press **Ctrl+Shift+V** or **Ctrl+`** to open the clipboard history
4. Click an item or press a number key to paste it instantly

---

## Shortcuts

| Key             | Action                                 |
| --------------- | -------------------------------------- |
| `Ctrl+Shift+V`  | Open clipboard history                 |
| `Ctrl+`` `      | Open clipboard history                 |
| `1` ~ `9` / `0` | Instantly paste the corresponding item |
| `ESC`           | Close list / clear search              |
| Right-click     | Pin · Edit · Add Tag · Delete menu     |

---

## Supported Environments

* Windows 10 / 11
* Linux — GNOME Wayland, X11

---

## Download

Download the latest version from:

https://github.com/iyagicom/ClipIyagi-dev/releases

---

## License

Copyright © 2026 IYAGI INC. All rights reserved.

Distributed as executable files only. Source code is not publicly available.
Personal and commercial use is freely permitted.
Unauthorized redistribution, modification, or reverse engineering is prohibited.

---

## Contact

* Email: [iyagicom@gmail.com](mailto:iyagicom@gmail.com)
* GitHub: https://github.com/iyagicom
