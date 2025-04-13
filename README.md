# archlinux-logout

A graphical logout and lock screen utility for Arch Linux, maintained by Sugarcrisp-ui. Provides a menu for logout, shutdown, reboot, suspend, hibernate, and lock, with support for `i3lock-color` and optional `betterlockscreen`.

## Prerequisites

- Arch Linux with an AUR helper (`paru` recommended).
- Dependencies: `python`, `python-gobject`, `libwnck3`, `python-psutil`, `python-cairo`, `python-distro`, `i3lock-color`.
- Optional: `betterlockscreen` for enhanced lock screen features.
- A `~/dotfiles/.config/` directory for config storage (optional).

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Sugarcrisp-ui/archlinux-logout.git
   cd archlinux-logout

2. Install dependencies:
   ```bash
   paru -S --needed python python-gobject libwnck3 python-psutil python-cairo python-distro i3lock-color

3. Build the package:
   ```bash
   makepkg -scrf

4. Install the package:
   ```bash
   sudo pacman -U archlinux-logout-1.0-4-any.pkg.tar.zst

5. Verify installation:
   ```bash
   ls -l /usr/bin/archlinux-logout /usr/bin/archlinux-betterlockscreen
   ls -l /etc/archlinux-logout.conf
   ls -l /usr/share/doc/archlinux-logout/

   Test the utility:
   ```bash
   archlinux-logout
