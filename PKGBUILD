# Maintainer: uberushaximus <uberushaximus AT gmail DOT com>
# Maintainer: Gaetan Bisson <bisson@archlinux.org>
# Contributor: Pierre Schmitz <pierre@archlinux.de>
# Contributor: Bug <Bug2000@gmail.com>

pkgname=libotr-git
pkgver=4.0.0.1.r10.g3172d79
pkgrel=1
pkgdesc='Off-the-Record Messaging Library and Toolkit'
url='https://otr.cypherpunks.ca/'
license=('GPL' 'LGPL')
arch=('i686' 'x86_64' 'arm' 'armv6h')
depends=('libgcrypt')
provides=('libotr')
conflicts=('libotr')
source=("git://git.code.sf.net/p/otr/libotr")
md5sums=(SKIP)
_gitname=libotr

pkgver() {
  cd $_gitname
  git describe --long --tags | sed -r 's/([^-]*-g)/r\1/;s/-/./g;s|_win32||g'
}

build() {
  cd "$srcdir/$_gitname"
  autoreconf -i
  ./configure --prefix=/usr --mandir=/usr/share/man
  make
}

package() {
  cd "$srcdir/$_gitname"
  make DESTDIR="$pkgdir" install
}
