pkgname=dectalk-git
_pkgname=dectalk
pkgver=4.62
pkgrel=1
pkgdesc="Text-to-speech software by Force/Fonix/SpeechFX (master branch)"
arch=("x86_64")
url="https://github.com/dectalk/dectalk"
options=(!lto)
conflicts=("dectalk")
provides=("dectalk")
license=("custom")
depends=()
optdepends=()
makedepends=(
  'gtk2>=2.24.33-2'
  'unzip>=6.0-18'
)
source=("dectalk::git+https://github.com/dectalk/dectalk.git#branch=install")
sha256sums=('SKIP')

build() {
  cd "$srcdir/$_pkgname/src"
  autoreconf -i
  ./configure
  make -j1
}

package() {
  cd "$srcdir/$_pkgname/src"
  make DESTDIR="$pkgdir" install

  install -m644 -Dt "${pkgdir}/usr/share/licenses/${pkgname}" "${srcdir}/$_pkgname/LICENCE"
}
