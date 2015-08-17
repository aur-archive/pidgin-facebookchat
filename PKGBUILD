# Maintainer: jsteel <mail at jsteel dot org>
# Contributor: Gadget3000 <gadget3000 at msn dot com>
# Contributor: Jarek jarek@eden.rutgers.edu
 
pkgname=pidgin-facebookchat
pkgver=1.69
pkgrel=3
pkgdesc="Facebook chat plugin for Pidgin and libpurple messengers"
url='http://code.google.com/p/pidgin-facebookchat'
license=('GPL3')
depends=('libpurple' 'json-glib')
arch=('i686' 'x86_64')
source=(http://pidgin-facebookchat.googlecode.com/files/$pkgname-source-$pkgver.tar.bz2)
md5sums=('e6855197f9cb3fc6540039b6d42841f6')
 
build() {
  [ "$CARCH" = "x86_64" ] && _flag="LINUX64_COMPILER=$CARCH-unknown-linux-gnu-gcc" && _arch=64

  cd "$srcdir"/$pkgname

  make $_flag libfacebook${_arch}.so
}

package() {
  [ "$CARCH" = "x86_64" ] && _arch=64

  install -Dm755 "$srcdir"/$pkgname/libfacebook${_arch}.so "$pkgdir"/usr/lib/purple-2/libfacebook${_arch}.so 
}
