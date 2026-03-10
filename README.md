# ClipIyagi (클립이야기)

Lightweight **clipboard history manager** for Windows and Linux.

ClipIyagi automatically saves text and images copied to the clipboard and lets you quickly paste them again using a global shortcut.

---

## ✨ Features

* **Clipboard history** — automatically stores copied text and images
* **Global hotkey** — open clipboard list anywhere
* **Instant paste** — selecting an item automatically pastes into the previous window
* **Number shortcuts** — press `1–9` or `0` to paste instantly
* **Search** — real-time text search
* **Image preview** — hover to see full image
* **Infinite scroll** — smooth browsing of large histories
* **System tray integration**

---

## ⚡ Quick Start (Linux)

Download the Linux binary and run:

```bash
chmod +x clipiyagi
./clipiyagi
```

---

## 🖥 Platforms

Supported platforms:

* Windows
* Linux (GNOME / X11)

---

## ⬇ Download

### Linux

Download the binary from GitHub Releases.

After downloading:

```bash
chmod +x clipiyagi
./clipiyagi
```

---

### Windows

Install from Microsoft Store.

(스토어 링크 추가 예정)

---

## 🎮 Keyboard Shortcuts

| Key              | Function                    |
| ---------------- | --------------------------- |
| Ctrl + Shift + V | Open clipboard list         |
| Ctrl + `         | Open clipboard list         |
| 1–9 / 0          | Paste selected history item |
| ESC              | Close list                  |

---

## 🐧 Linux Notes

Some clipboard automation features require additional tools depending on the session type.

### Wayland (GNOME)

Install required tools:

```bash
sudo apt install ydotool wl-clipboard
```

Run the ydotool daemon:

```bash
ydotoold &
```

### X11

Install:

```bash
sudo apt install xdotool
```

---

## 📌 Notes

* Runs in the system tray
* Automatically stores clipboard history
* Settings are saved automatically
* Supports both text and images

---

## 👤 Author

IYAGI INC
Email: [iyagicom@gmail.com](mailto:iyagicom@gmail.com)
GitHub: https://github.com/iyagicom

---

## 📜 License

Copyright (c) 2026 IYAGI INC

All rights reserved.

This software is provided as **executable files only**.
The source code is not publicly available.

You may use this software for personal and non-commercial purposes.

Redistribution, modification, or reverse engineering is prohibited without explicit written permission from the author.
