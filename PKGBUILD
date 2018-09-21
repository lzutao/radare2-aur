# Maintainer: lzutao <1stpangu@gmail.com>
pkgname="radare2-latest"
pkgver=2.9.0.r171.g555385030
pkgrel=1
pkgdesc="Advanced commandline hexadecimal editor, disassembler and debugger"
arch=('x86_64')
url="http://www.radare.org/"
license=('LGPL3')
depends=(
  'capstone'
  'openssl'
  'libzip'
)
makedepends=('git')
optdepends=(
  'libuv'
  'gmp'
)
provides=('radare2')
conflicts=('radare2')
options=('!libtool')

source=("${pkgname}-${pkgver}"::"git://github.com/radare/radare2.git")
md5sums=('SKIP')

pkgver() {
  cd "${pkgname}-${pkgver}"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd "${pkgname}-${pkgver}"
  ./sys/build.sh
}

package() {
  cd "${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}/" symstall
}
