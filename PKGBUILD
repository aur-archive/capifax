# Contributor: Bernhard Walle <bernhard.walle@gmx.de>
# Maintainer: Bjoern Franke <bjo@nord-west.org>
# AUR Category: lib

pkgname=capifax
pkgver=0.7.3
pkgrel=4
pkgdesc="capifax is an application to fax over capi via soft DSP (spandsp)."
url="http://www.tabos.org/ffgtk/"
license="GPL"
depends=('libcapi20' 'spandsp' 'libtiff')
makedepends=('libcapi20' 'spandsp')
arch=(i686 x86_64)
install=(capifax.install)
source=(http://www.tabos.org/ffgtk/download/${pkgname}-${pkgver}-jmb4.tar.bz2)
md5sums=('05094feb1ef6f8dbe65643c43d7b648c')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./configure --prefix=/usr --sysconfdir=/etc
  make || return 1
  make DESTDIR=${pkgdir} install || return 1
  install -d ${pkgdir}/usr/sbin/ || return 1
  cp ${srcdir}/${pkgname}-${pkgver}/cups/capifax-cups ${pkgdir}/usr/sbin/ || return 1
}
