# Maintainer: Your Name <youremail@domain.com>
pkgname=dmenu-custom
pkgver=5.0.a55b2af
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
source=('arg.h' 'config.h' 'config.mk' 'dmenu.1' 'dmenu.c' 'drw.c' 'drw.h' 'LICENSE' 'Makefile' 'README' 'util.c' 'util.h' 'stest.c' 'stest.1' 'dmenu_path' 'dmenu_run')
noextract=("${source[@]%%::*}")
md5sums=("${source[@]/*/SKIP}")
validpgpkeys=()

pkgver() {
	printf "%s.%s" "$(awk '/^VERSION =/ {print $3}' config.mk)" "$(git rev-parse --short HEAD)"
}

check() {
	git diff --exit-code -- ':/*' ':/!PKGBUILD'
}

build() {
	make
}

package() {
	make PREFIX="/usr" DESTDIR="$pkgdir" install
}
