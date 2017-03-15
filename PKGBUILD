# $Id$
# Maintainer: BlackEagle < ike DOT devolder AT gmail DOT com >
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Martin Striz < ms AT martinstriz DOT cz >
# Contributor: Jarek Sedlacek <jareksedlacek@gmail.com>

pkgname=php-mongodb
pkgver=1.2.7
pkgrel=1
pkgdesc="MongoDB driver for PHP"
arch=("i686" "x86_64")
url="http://mongodb.github.io/mongo-php-driver"
license=("Apache")
#depends=('php' 'libmongoc')
depends=('php')
makedepends=('re2c')
backup=("etc/php/conf.d/mongodb.ini")
install=php-mongodb.install
source=(
	"https://pecl.php.net/get/mongodb-$pkgver.tgz"
	"mongodb.ini"
)
sha256sums=('2b968f08369ba17fb28e204bc5d48a50fb545f7d06a71acc510aa563610fdd2d'
            '242b9ffea6bd84f813c7fc2a767eaa89f83577c5ff10ff36aecec2ca308ff72b')

build() {
	cd mongodb-$pkgver
	phpize
	#./configure --prefix=/usr --with-libbson --with-libmongoc
	./configure --prefix=/usr
}

package() {
	cd mongodb-$pkgver
	make INSTALL_ROOT="$pkgdir" install
	install -Dm644 "$srcdir/mongodb.ini" "$pkgdir/etc/php/conf.d/mongodb.ini"
}
