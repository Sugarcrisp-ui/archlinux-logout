# Maintainer: Sugarcrisp-ui <brettcrisp2@gmail.com>
pkgname=archlinux-logout
pkgver=1.0
pkgrel=4
pkgdesc="Graphical logout and lock screen utility for Arch Linux, maintained by Sugarcrisp-ui"
arch=('any')
url="https://github.com/Sugarcrisp-ui/archlinux-logout"
license=('GPL3')
depends=('python' 'python-gobject' 'libwnck3' 'python-psutil' 'python-cairo' 'python-distro' 'i3lock-color')
install=archlinux-logout.install
source=(
  'archlinux-logout.install'
  'archlinux-logout-files.tar.gz'
)
noextract=('archlinux-logout-files.tar.gz')
sha256sums=(
  'e1f5ef275d79b086504e02ac4f4f33c0e72184ca5af65f42fbe331e5ec098725'
  '527a10f8fe5bb90c52d3b1900a91b1e9f4bdf1b1a9d81a5c7309f11fa59a9f40'
)

package() {
  # Extract tarball
  tar -xzf "$srcdir/archlinux-logout-files.tar.gz" -C "$srcdir"

  # Install config
  install -Dm644 "$srcdir/etc/archlinux-logout.conf" "$pkgdir/etc/archlinux-logout.conf"

  # Install binaries
  install -Dm755 "$srcdir/usr/bin/archlinux-logout" "$pkgdir/usr/bin/archlinux-logout"
  install -Dm755 "$srcdir/usr/bin/archlinux-betterlockscreen" "$pkgdir/usr/bin/archlinux-betterlockscreen"

  # Install desktop file
  install -Dm644 "$srcdir/usr/share/applications/archlinux-betterlockscreen.desktop" \
    "$pkgdir/usr/share/applications/archlinux-betterlockscreen.desktop"

  # Install Python files
  install -d "$pkgdir/usr/share/archlinux-logout"
  cp -r "$srcdir/usr/share/archlinux-logout/"*.py "$pkgdir/usr/share/archlinux-logout/"

  install -d "$pkgdir/usr/share/archlinux-betterlockscreen"
  cp -r "$srcdir/usr/share/archlinux-betterlockscreen/"*.py "$pkgdir/usr/share/archlinux-betterlockscreen/"

  # Install images and wallpapers
  install -d "$pkgdir/usr/share/archlinux-betterlockscreen/images"
  cp -r "$srcdir/usr/share/archlinux-betterlockscreen/images/"* "$pkgdir/usr/share/archlinux-betterlockscreen/images/"

  install -d "$pkgdir/usr/share/archlinux-betterlockscreen/wallpapers"
  cp -r "$srcdir/usr/share/archlinux-betterlockscreen/wallpapers/"* "$pkgdir/usr/share/archlinux-betterlockscreen/wallpapers/"

  # Install themes
  install -d "$pkgdir/usr/share/archlinux-logout-themes"
  cp -r "$srcdir/usr/share/archlinux-logout-themes/"* "$pkgdir/usr/share/archlinux-logout-themes/"

  # Install icon
  install -Dm644 "$srcdir/usr/share/icons/hicolor/scalable/apps/better-lock-screen.svg" \
    "$pkgdir/usr/share/icons/hicolor/scalable/apps/better-lock-screen.svg"

  # Install documentation
  install -d "$pkgdir/usr/share/doc/archlinux-logout"
  cp -r "$srcdir/usr/share/doc/archlinux-logout/"* "$pkgdir/usr/share/doc/archlinux-logout/"
}
