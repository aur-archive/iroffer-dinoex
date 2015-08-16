# Maintainer: kevku <kevku@gmx.com>
pkgname=iroffer-dinoex
pkgver=3.30
pkgrel=1
pkgdesc="IRC Bot to share files via DCC"
arch=('x86_64' 'i686')
url="http://iroffer.dinoex.net"
license=('GPL2' 'LGPL2.1' 'MIT' 'BSD')
depends=('openssl')
optdepends=('curl: for the FETCH-Command'
	    'ruby: RUBY scripting support'
	    'geoip: for IP to Country'
	    'miniupnpc: for NAT Routers')
source=("http://iroffer.dinoex.net/$pkgname-$pkgver.tar.gz")
md5sums=('646bc7e579cf82d0ba4795c495e7e0b0')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./Configure -curl -geoip -ruby -upnp PREFIX=/usr LOCALBASE=/usr
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  install -D -m 0755 iroffer $pkgdir/usr/bin/iroffer
  install -D LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
  install -D iroffer.1 $pkgdir/usr/share/man/man1/iroffer.1
  mkdir -p $pkgdir/usr/share/doc/iroffer
  cp -r {sample.config,ruby-sample.rb,README*,htdocs,help-admin-en.txt,*.html} $pkgdir/usr/share/doc/iroffer
}
