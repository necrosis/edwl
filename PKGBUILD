pkgname=edwl
pkgver=0.9.1
pkgrel=1
pkgdesc='A simple dynamic window manager for wayland.'
arch=('x86_64')
license=('GPL3')
depends=(wlroots wayland libxkbcommon libinput cairo pango systemd-libs libgcrypt libjpeg-turbo xorg-xwayland)
url=https://gitlab.com/necrosis/edwl
source=("edwl.tar.gz::https://gitlab.com/necrosis/edwl/-/archive/$pkgver/edwl-$pkgver.tar.gz"
	"edwl.desktop")

sha256sums=(
'ee118850d1557c5cbd22f81aa2feeccae637aee0df076a40237ade19f4f89531'
'5890c032ae202361f126b2a3853be4de3528fcd677a247a7d891cd12d030f587'
)


build() {
  tar xfz edwl.tar.gz
  cd edwl-$pkgver
  make
}

package() {
  install -Dm655 "edwl-$pkgver/edwl" -t "$pkgdir/usr/bin/"
  install -Dm644 "edwl.desktop" -t "$pkgdir/usr/share/wayland-sessions/"
  install -Dm644 "edwl-$pkgver/LICENSE" -t "$pkgdir/usr/share/licenses/$pkgname"
}
