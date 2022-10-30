pkgname=edwl
pkgver=0.9.5
pkgrel=1
pkgdesc='A simple dynamic window manager for wayland.'
arch=('x86_64')
license=('GPL3')
depends=(wlroots wayland libxkbcommon libinput cairo pango systemd-libs libjpeg-turbo xorg-xwayland)
url=https://gitlab.com/necrosis/edwl
source=("edwl.tar.gz::https://gitlab.com/necrosis/edwl/-/archive/$pkgver/edwl-$pkgver.tar.gz"
	"edwl.desktop")

sha256sums=(
'd3c265b291f970da7908bc10bdd69d724d0d5a897f9a7c3b25d5503bf3b17d50'
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
  install -Dm644 "edwl-$pkgver/background.png" -t "$pkgdir/usr/local/share/edwl/"
  install -Dm644 "edwl-$pkgver/LICENSE" -t "$pkgdir/usr/share/licenses/$pkgname"
}
