
pkgname="cntlm"
pkgver=0.92.3
pkgrel=3
license=('GPL2')
pkgdesc="An NTLM, NTLM2SR, and NTLMv2 authenticating HTTP proxy"
arch=('i686' 'x86_64')
url="http://cntlm.sourceforge.net"
source=("http://downloads.sourceforge.net/project/$pkgname/$pkgname/$pkgname%20$pkgver/$pkgname-$pkgver.tar.gz"
	'cntlm.service')
backup=('etc/cntlm.conf')
md5sums=('0d7fcfbfbef0546306b896be246caa88'
		'36f88f6ebde5d1c57d9847fedcf71b84')

build() {
	cd "$srcdir/$pkgname-$pkgver"
	./configure
	make
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	make \
		SYSCONFDIR="$pkgdir/etc" \
		BINDIR="$pkgdir/usr/bin" \
		MANDIR="$pkgdir/usr/share/man" \
		install
	install -Dm 644 "$srcdir/cntlm.service" "$pkgdir/usr/lib/systemd/system/cntlm.service"
}
