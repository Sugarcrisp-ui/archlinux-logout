# Maintainer: Sugarcrisp-ui <your.email@example.com>
pkgname=archlinux-logout
pkgver=1.0
pkgrel=1
pkgdesc="Graphical logout and lock screen utility for Arch Linux, maintained by Sugarcrisp-ui"
arch=('any')
url="https://github.com/Sugarcrisp-ui/archlinux-logout"
license=('GPL3')
depends=('python' 'python-gobject' 'libwnck3' 'python-psutil' 'python-cairo' 'python-distro' 'i3lock')
optdepends=('betterlockscreen: for enhanced lock screen features')
source=('local::.')
install='archlinux-logout.install'
sha256sums=('SKIP')

package() {
  # Binaries
  install -Dm755 usr/bin/archlinux-logout "${pkgdir}/usr/bin/archlinux-logout"
  install -Dm755 usr/bin/archlinux-betterlockscreen "${pkgdir}/usr/bin/archlinux-betterlockscreen"

  # Logout scripts
  install -Dm755 usr/share/archlinux-logout/archlinux-logout.py "${pkgdir}/usr/share/archlinux-logout/archlinux-logout.py"
  install -Dm644 usr/share/archlinux-logout/Functions.py "${pkgdir}/usr/share/archlinux-logout/Functions.py"
  install -Dm644 usr/share/archlinux-logout/GUI.py "${pkgdir}/usr/share/archlinux-logout/GUI.py"

  # Betterlockscreen scripts
  install -Dm755 usr/share/archlinux-betterlockscreen/archlinux-betterlockscreen.py "${pkgdir}/usr/share/archlinux-betterlockscreen/archlinux-betterlockscreen.py"
  install -Dm644 usr/share/archlinux-betterlockscreen/Functions.py "${pkgdir}/usr/share/archlinux-betterlockscreen/Functions.py"
  install -Dm644 usr/share/archlinux-betterlockscreen/GUI.py "${pkgdir}/usr/share/archlinux-betterlockscreen/GUI.py"
  install -Dm644 usr/share/archlinux-betterlockscreen/Splash.py "${pkgdir}/usr/share/archlinux-betterlockscreen/Splash.py"
  install -Dm644 usr/share/archlinux-betterlockscreen/Support.py "${pkgdir}/usr/share/archlinux-betterlockscreen/Support.py"

  # Desktop file
  install -Dm644 usr/share/applications/archlinux-betterlockscreen.desktop "${pkgdir}/usr/share/applications/archlinux-betterlockscreen.desktop"

  # Themes and images
  install -d "${pkgdir}/usr/share/archlinux-logout-themes/themes"
  cp -r usr/share/archlinux-logout-themes/themes/* "${pkgdir}/usr/share/archlinux-logout-themes/themes/"
  install -Dm644 usr/share/archlinux-logout-themes/configure.svg "${pkgdir}/usr/share/archlinux-logout-themes/configure.svg"
  install -Dm644 usr/share/archlinux-logout-themes/configure_blur.svg "${pkgdir}/usr/share/archlinux-logout-themes/configure_blur.svg"
  install -Dm644 usr/share/archlinux-logout-themes/light.svg "${pkgdir}/usr/share/archlinux-logout-themes/light.svg"
  install -Dm644 usr/share/archlinux-logout-themes/light_blur.svg "${pkgdir}/usr/share/archlinux-logout-themes/light_blur.svg"
  install -Dm644 usr/share/archlinux-logout-themes/wallpaper.jpg "${pkgdir}/usr/share/archlinux-logout-themes/wallpaper.jpg"

  # Betterlockscreen assets
  install -d "${pkgdir}/usr/share/archlinux-betterlockscreen/images"
  cp -r usr/share/archlinux-betterlockscreen/images/* "${pkgdir}/usr/share/archlinux-betterlockscreen/images/"
  install -d "${pkgdir}/usr/share/archlinux-betterlockscreen/wallpapers"
  cp -r usr/share/archlinux-betterlockscreen/wallpapers/* "${pkgdir}/usr/share/archlinux-betterlockscreen/wallpapers/"

  # Icons
  install -d "${pkgdir}/usr/share/icons/hicolor"
  cp -r usr/share/icons/hicolor/* "${pkgdir}/usr/share/icons/hicolor/"

  # Config file
  install -Dm644 etc/archlinux-logout.conf "${pkgdir}/etc/archlinux-logout.conf"
}
