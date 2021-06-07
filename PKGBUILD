# Maintainer: knsrinath <knsrinath2005@gmail.com>
pkgname=dmenu-srinath
pkgver=5.0
pkgrel=1
epoch=
pkgdesc="A build of dmenu patched for numbers, mouse support."
arch=(x86_64)
url="https://github.com/knsrinath/dmenu-srinath.git"
license=('MIT')
groups=()
depends=(ttf-jetbrains-mono)
makedepends=(git make)
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
    printf "5.0" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd dmenu-srinath
    make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
    cd dmenu-srinath  
    mkdir -p ${pkgdir}/opt/${pkgname}
    cp -rf * ${pkgdir}/opt/${pkgname}
    make PREFIX=/usr DESTDIR="${pkgdir}" install
    install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    install -Dm644 README.org "${pkgdir}/usr/share/doc/${pkgname}/README.org"
}
