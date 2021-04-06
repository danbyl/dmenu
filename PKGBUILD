# Maintainer: Your Name <youremail@domain.com>
pkgname=dmenu-custom
_pkgname=dmenu-custom
pkgver=4.9.fffc9d7
pkgrel=1
pkgdesc="My own build of dmenu, with fuzzy matching and mouse support"
arch=('x86_64')
url="https://github.com/danbyl/dmenu"
license=('MIT')
depends=('sh' 'libxinerama' 'libxft-bgra' 'freetype2')
makedepends=('git')
checkdepends=()
provides=('dmenu')
conflicts=('dmenu')
replaces=('dmenu')
install=
changelog=
source=('git+ssh://git@github.com/danbyl/dmenu.git')
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
	cd "$srcdir/$_pkgname"
	printf "%s.%s" "$(awk '/^VERSION =/ {print $3}' config.mk)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$_pkgname"
	make
}

package() {
	cd "$_pkgname"
	make PREFIX="/usr" DESTDIR="$pkgdir" install
}
