# $Id$
# Maintainer: BlackEagle < ike DOT devolder AT gmail DOT com >
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Martin Striz < ms AT martinstriz DOT cz >
# Contributor: Jarek Sedlacek <jareksedlacek@gmail.com>

pkgname=php-mongodb
pkgver=1.3.2
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
sha256sums=('3a24f60c1bfd68736977e53f40cd5b50eccf42472277ce8101ca7eea0fe82788'
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
