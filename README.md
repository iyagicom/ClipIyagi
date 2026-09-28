# ClipIyagi

**Never lose something you copied. A clipboard manager for Windows and Linux — text and images, one hotkey away.**

[English](README.md) · [한국어](README_ko.md)

![ClipIyagi](clipiyagi1.png)

## Why ClipIyagi?

- **Everything you copy is kept.** Text and images are recorded automatically — go back to the link you copied an hour ago.
- **One hotkey, from anywhere.** `Ctrl+Shift+V` opens the list over whatever you're doing. Press `1`–`9` and it's pasted.
- **It pastes for you.** Pick an item and it lands in the window you were typing in. Works in terminals too.
- **Keep what matters on top.** Pin frequently used snippets, tag them, filter with `#tag`, edit them in place.
- **Wayland without extra tools.** On GNOME and KDE Plasma auto-paste works with nothing else to install — no xdotool, no ydotool.

## Features

- Automatic text and image history (100 / 300 / 500 / 1000 / unlimited)
- Pin, edit, tag and delete items; real-time search
- Global hotkey, number-key paste, auto-paste into the previous window
- Choose `Ctrl+V` or `Ctrl+Shift+V` as the paste key
- Hover preview for long text; emoji shown in color
- Dark mode, font size, resizable window
- System tray, start on login

| | |
|---|---|
| ![](clipiyagi2.png) | ![](clipiyagi3.png) |

## Download

**[⬇ Latest release](https://github.com/iyagicom/ClipIyagi/releases/latest)**

| Your system | File to pick |
|---|---|
| Windows 10 / 11 | [Microsoft Store](https://apps.microsoft.com/detail/9N2SL0RVX6CN) |
| Ubuntu 24.04 · Debian | `.deb` marked **ubuntu24.04** |
| Ubuntu 26.04 | `.deb` marked **ubuntu26.04** |
| Fedora · openSUSE | `.rpm` |
| Arch · Manjaro | `.pkg.tar.zst` |
| Any other Linux | `.AppImage` (run without installing) or `.zip` |

```bash
sudo apt install ./clipiyagi_*_amd64.deb     # Ubuntu / Debian
sudo dnf install ./clipiyagi-*.rpm           # Fedora
sudo pacman -U clipiyagi-*.pkg.tar.zst       # Arch
```

On Linux, auto-paste works out of the box on X11, GNOME and KDE Plasma (the first time, GNOME/KDE ask once for permission). On sway, Hyprland and other wlroots desktops it uses `wtype` if installed.

## License

[License](LICENSE) · [Privacy policy](privacy-policy.md)
