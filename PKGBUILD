
pkgname='lockbook-desktop'
_pkgname="lockbook-desktop"
pkgver=0.7.2
pkgrel=2
arch=('any')
url="https://github.com/lockbook/lockbook"
pkgdesc="The private, polished note-taking platform."
license=('BSD-3-Clause')
makedepends=('cargo' 'git' 'cmake' 'base-devel')
depends=()
provides=('lockbook-desktop')
conflicts=('lockbook-desktop')
source=("git+https://github.com/lockbook/aur-lockbook-desktop.git" "git+https://github.com/lockbook/lockbook.git#tag=$pkgver")
sha256sums=('SKIP' 'SKIP')
groups=('lockbook')

pkgver() {
  echo "0.7.2"
}

build() {
  echo $_pkgname
  cd $srcdir/lockbook/clients/egui
  cargo build --release --locked
}

package() {
  install -D -m755 "$srcdir/lockbook/target/release/lockbook-egui" "$pkgdir/usr/bin/lockbook-desktop"
  install -D -m644 "$srcdir/aur-lockbook-desktop/light-1-tranparent.png" "$pkgdir/usr/share/pixmaps/light-1-tranparent.png"
  install -D -m644 "$srcdir/aur-lockbook-desktop/lockbook-desktop.desktop" "$pkgdir/usr/share/applications/lockbook-desktop.desktop"
}
