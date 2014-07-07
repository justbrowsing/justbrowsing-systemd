# Maintainer: justbrowsing <developer4linux+aur@gmail.com>
pkgname=justbrowsing-systemd
pkgver=1.0
pkgrel=2
pkgdesc="SystemD Unit files and boot script to start JustBrowsing session"
arch=('any')
url="https://github.com/justbrowsing/justbrowsing-systemd"
license=('GPL3')
depends=('systemd' 'polkit')
optdepends=('jb-config: load/save and manage settings')
groups=("justbrowsing")
source=("https://github.com/justbrowsing/${pkgname}/archive/master.zip")
install="jb-systemd.install"
md5sums=('SKIP')
 
package() {
  cd "$srcdir/${pkgname}-master"

  # Boot script
  mkdir -p "$pkgdir/usr/bin"
  install -Dm755 restoreboot "$pkgdir/usr/bin/restoreboot"

  # Polkit rule
  mkdir -p "$pkgdir/etc/polkit-1/rules.d"
  install -Dm644 00-timezone.rules "$pkgdir/etc/polkit-1/rules.d/00-timezone.rules"

  # Unit files
  mkdir -p "$pkgdir/usr/lib/systemd/system"
  install -Dm644 autologin@.service "$pkgdir/usr/lib/systemd/system/autologin@.service"
  install -Dm644 restoreboot.service "$pkgdir/usr/lib/systemd/system/restoreboot.service"
  install -Dm644 savejb-daemon.service "$pkgdir/usr/lib/systemd/system/savejb-daemon.service"
}


