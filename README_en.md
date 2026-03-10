ClipIyagi
Clipboard history manager — Windows / Linux (GNOME) support

Automatically saves text and images, and lets you open the history list with a single shortcut to quickly paste items.

Features
Automatic clipboard saving — Records both text and images

Global hotkeys — Ctrl+Shift+V or `Ctrl+\`` to open anywhere

Auto-paste — Instantly pastes into the previous window when selecting an item

Numeric shortcuts — Press 1–9, 0 to select directly while the list is open

Search — Real-time search through text contents

Image preview — Hover over thumbnails to see the original popup

Infinite scroll — Quickly browse large histories

System tray support

Build
Requirements
Item	Version
Qt	6.x (Core, Widgets, Gui, DBus)
CMake	3.16+
Compiler	GCC / MSVC / MinGW
Build steps
bash
cmake -B build/linux-release -DCMAKE_BUILD_TYPE=Release
cmake --build build/linux-release --parallel
./build/linux-release/ClipIyagi
Linux Installation Guide
Required packages
bash
sudo apt install ydotool wl-clipboard xdotool
Package	Purpose
ydotool	Auto-paste on Wayland (sends Ctrl+V)
wl-clipboard	Clipboard persistence on Wayland (wl-copy)
xdotool	Auto-paste on X11 sessions
On Fedora / Arch, install with dnf / pacman using the same package names.

Wayland (GNOME) extra setup — for auto-paste
Since ydotool works at the kernel input level, you need to add yourself to the input group and re-login:

bash
# 1. Add to input group (one-time)
sudo usermod -a -G input $USER

# 2. After re-login, start ydotoold daemon
ydotoold &
To keep auto-paste working after reboot, either run ydotoold & manually each time or add it to ~/.bashrc.

Global hotkeys (GNOME Wayland)
On GNOME Wayland, custom hotkeys are automatically registered via gsettings when the app runs.
You can use Ctrl+Shift+V (or the shortcut chosen in the tray) without extra setup.

How it works:

Hotkey → launches a second ClipIyagi instance

D-Bus sends a toggle signal to the first running instance

Window toggles

Platform Support
✅ Windows
Feature	Status
Clipboard monitoring	✅
Global hotkeys	✅ (Ctrl+Shift+V / `Ctrl+\``)
Auto-paste	✅
System tray	✅
Auto-start	✅ (Registry)
✅ Linux — GNOME Wayland (Ubuntu 22.04+)
Feature	Status	Notes
Clipboard monitoring	✅	
Global hotkeys	✅	gsettings auto-registration
Auto-paste	✅	Requires ydotool + wl-copy
System tray	✅	XCB XEMBED (raw)
Auto-start	⚠️	Manual setup required
⚠️ Not working on GNOME Wayland
Tool	Reason
xdotool	_NET_ACTIVE_WINDOW unsupported — cannot detect active window
wtype	GNOME does not support zwp_virtual_keyboard_v1 protocol
→ Auto-paste must use ydotool + ydotoold daemon.

⚠️ Linux — KDE / Other Wayland
Global hotkeys may not work (registered via GNOME gsettings).
System tray icon works normally.

✅ Linux — X11 sessions
Feature	Status	Notes
Clipboard monitoring	✅	
Global hotkeys	✅	XCB hotkey grab
Auto-paste	✅	Requires xdotool
System tray	✅	
