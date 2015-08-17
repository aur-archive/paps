# Maintainer: Gaetan Bisson <bisson@archlinux.org>
# Contributor: Tim Yang <tdy@gmx.com>
# Contributor: Artyom 'logus' Pervukhin <logus9@gmail.com>

pkgname=paps
pkgver=0.6.8
pkgrel=4
pkgdesc='UTF-8 to PostScript converter via Pango'
url='http://paps.sourceforge.net/'
license=('LGPL')
depends=('pango')
arch=('i686' 'x86_64' 'armv7h')
source=("http://downloads.sourceforge.net/paps/paps-${pkgver}.tar.gz")
sha1sums=('83646b0de89deb8321f260c2c5a665bc7c8f5928')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	export LDFLAGS=${LDFLAGS/,--as-needed/}
	./configure --prefix=/usr --mandir=/usr/share/man --disable-static
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="${pkgdir}" install
}
