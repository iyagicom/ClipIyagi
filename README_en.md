# ClipIyagi

> Clipboard History Manager — Windows / Linux (GNOME) Support

Automatically saves text and images to clipboard history, and lets you instantly browse and paste with a single shortcut.

---

## Features

- **Auto-save clipboard** — Records both text and images
- **Global hotkey** — Open from anywhere with `Ctrl+Shift+V` or `` Ctrl+` ``
- **Auto-paste** — Automatically pastes to the previous window upon item selection
- **Number shortcuts** — Press `1`–`9`, `0` to select items while the list is open
- **Search** — Real-time search through text content
- **Image preview** — Hover over a thumbnail to see a full-size popup
- **Infinite scroll** — Quickly browse large histories
- **System tray** — Runs in the background

---

## Build

### Requirements

| Item | Version |
|------|---------|
| Qt | 6.x (Core, Widgets, Gui, DBus) |
| CMake | 3.16+ |
| Compiler | GCC / MSVC / MinGW |

## Linux Installation

### Required Packages

```bash
sudo apt install ydotool wl-clipboard xdotool
```

| Package | Purpose |
|---------|---------|
| `ydotool` | Auto-paste on Wayland (sends Ctrl+V) |
| `wl-clipboard` | Clipboard persistence on Wayland (`wl-copy`) |
| `xdotool` | Auto-paste on X11 sessions |

> **Fedora / Arch**: Install the same package names using `dnf` / `pacman`.

---

### Wayland (GNOME) — Additional Setup for Auto-Paste

ydotool operates at the kernel input level, so you need to **add yourself to the input group and re-login**.

```bash
# 1. Add user to input group (one-time setup)
sudo usermod -a -G input $USER

# 2. After re-login, start the ydotoold daemon
ydotoold &
```

> To keep auto-paste working after reboot, run `ydotoold &` each session
> or add it to `~/.bashrc`.

---

### Global Hotkey (GNOME Wayland)

On GNOME Wayland, a **gsettings custom shortcut** is automatically registered at launch.
You can use `Ctrl+Shift+V` (or the shortcut selected in the tray) without any manual setup.

How it works:
1. Hotkey → launches a second ClipIyagi instance
2. The new instance sends a Toggle signal via D-Bus to the running first instance
3. Window toggles

---

## Platform Support

### ✅ Windows

| Feature | Status |
|---------|--------|
| Clipboard monitoring | ✅ |
| Global hotkey | ✅ (`Ctrl+Shift+V` / `` Ctrl+` ``) |
| Auto-paste | ✅ |
| System tray | ✅ |
| Auto-start | ✅ (Registry) |

---

### ✅ Linux — GNOME Wayland (Ubuntu 22.04+)

| Feature | Status | Notes |
|---------|--------|-------|
| Clipboard monitoring | ✅ | |
| Global hotkey | ✅ | Auto-registered via gsettings |
| Auto-paste | ✅ | Requires `ydotool` + `wl-copy` |
| System tray | ✅ | XCB XEMBED (raw) |
| Auto-start | ⚠️ | Manual registration required |

#### ⚠️ What does NOT work on GNOME Wayland

| Tool | Reason |
|------|--------|
| `xdotool` | No `_NET_ACTIVE_WINDOW` support — cannot detect active window |
| `wtype` | GNOME does not support `zwp_virtual_keyboard_v1` protocol |

→ Auto-paste requires `ydotool` + the `ydotoold` daemon.

---

### ⚠️ Linux — KDE / Other Wayland Compositors

Global hotkeys may not work (registration uses the GNOME gsettings method).
Tray icon click works normally.

---

### ✅ Linux — X11 Session

| Feature | Status | Notes |
|---------|--------|-------|
| Clipboard monitoring | ✅ | |
| Global hotkey | ✅ | XCB hotkey grab |
| Auto-paste | ✅ | Requires `xdotool` |
| System tray | ✅ | 

## License
GPL-3.0 license

