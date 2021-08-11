origname=libchewing
pkgname=$origname-dvhsu
pkgver=0.5.1
pkgrel=11
pkgdesc="a small patch to make dvorak hsu's keyboard functional"
arch=('x86_64')
depends=('sqlite')
source=("https://github.com/chewing/$origname/releases/download/v$pkgver/$origname-$pkgver.tar.bz2")
license=('LGPL2.1')
conflicts=("$origname")
provides=("$origname")
sha256sums=('9708c63415fa6034435c0f38100e7d30d0e1bac927f67bec6dfeb3fef016172b')

prepare() {
    cd "$origname-$pkgver"
    patch -p0 -i ../../dvhsu.patch
}

build() {
    cd "$origname-$pkgver"
    ./configure --libdir=/usr/lib
    make
}

check() {
    cd "$origname-$pkgver"
    make check
}

package() {
    cd "$origname-$pkgver"
    make DESTDIR="$pkgdir/" install
}

