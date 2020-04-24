# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname=('dmenu-custom')
pkgver=4.9
pkgrel=1
pkgdesc="My own build of dmenu, a generic menu for X"
arch=('x86_64')
url="https://tools.suckless.org/dmenu/"
license=('GPL')
depends=('sh' 'libxinerama' 'libxft' 'freetype2')
makedepends=()
checkdepends=()
provides=('dmenu')
conflicts=('dmenu')
replaces=('dmenu')
install=
changelog=
source=("$pkgname-$pkgver.tar.gz"
        "$pkgname-$pkgver.patch")
noextract=()
md5sums=()
validpgpkeys=()

prepare() {
	cd "$pkgname-$pkgver"
	patch -p1 -i "$srcdir/$pkgname-$pkgver.patch"
}

build() {
	cd "$pkgname-$pkgver"
	./configure --prefix=/usr
	make
}

check() {
	cd "$pkgname-$pkgver"
	make -k check
}

package() {
	cd "$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
}
