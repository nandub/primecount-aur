# Maintainer: nandub <nandub+arch@nandub.info>
# Contributor: Kim Walisch <kim.walisch@gmail.com>

pkgname=primecount
pkgver=5.3
pkgrel=1
pkgdesc="Fast prime counting function implementations"
url="https://github.com/kimwalisch/primecount"
license=('BSD')
depends=('gcc-libs')
makedepends=('cmake')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/kimwalisch/primecount/archive/v${pkgver}.tar.gz")
sha1sums=('b9bd0cf65e7299ab79a4adc0985555a71943dc98')
arch=('x86_64')

build() {
  cd $pkgname-$pkgver
  cmake -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_INSTALL_LIBDIR=lib \
        -DBUILD_SHARED_LIBS=ON .
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install

  install -Dm644 "README.md" "$pkgdir/usr/share/doc/$pkgname/README.md"
  install -Dm644 "COPYING" "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
