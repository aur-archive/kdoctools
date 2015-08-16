# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kdoctools
pkgver=4.99.0
pkgrel=1
pkgdesc='KDocTools'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kdoctools'
license=('LGPL')
depends=('karchive' 'docbook-xsl')
makedepends=('extra-cmake-modules')
groups=('kf5')
options=('staticlibs')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('371c1e103bf63328a7237292fa9346e2')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
