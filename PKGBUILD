# $Id: PKGBUILD 173190 2012-12-12 12:47:29Z stephane $
# Maintainer: Stéphane Gaudreault <stephane@archlinux.org>
pkgname=serf
pkgver=1.1.1
pkgrel=1
pkgdesc="High-performance asynchronous HTTP client library"
url="http://code.google.com/p/serf/"
arch=('i686' 'x86_64')
license=('Apache')
depends=('apr' 'apr-util' 'openssl' 'zlib')
source=(http://serf.googlecode.com/files/${pkgname}-${pkgver}.tar.bz2)
sha1sums=('1ec4689ef57e7c28e7371df00d0ccc3e32ef6457')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  ./configure --prefix=/usr --with-apr=/usr --with-apr-util=/usr --with-openssl=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
  rm "${pkgdir}"/usr/lib/libserf-1.{a,la}
}
