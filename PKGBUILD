pkgname=dmenu-jpszc
pkgver=5.1.r2.611125f
pkgrel=1
epoch=
pkgdesc="A build of dmenu patched for centering, borders, grids, numbers, line height, mouse support, fuzzy matching and highlighting."
arch=(x86_64)
url="https://github.com/JPszC/dmenu-jpszc"
license=('MIT')
groups=()
depends=(ttf-hack ttf-joypixels)
makedepends=(git)
checkdepends=()
optdepends=()
provides=(dmenu)
conflicts=(dmenu)
replaces=()
backup=()
options=()
install=
changelog=
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
	cd "${_pkgname}"
    printf "5.1.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd dmenu-jpszc
    make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
    cd dmenu-jpszc  
    mkdir -p ${pkgdir}/opt/${pkgname}
    cp -rf * ${pkgdir}/opt/${pkgname}
    make PREFIX=/usr DESTDIR="${pkgdir}" install
}
