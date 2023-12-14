pkgname=jq
pkgver=1.7.1
pkgrel=1
pkgdesc='Command-line JSON processor'
arch=('x86_64')
url='https://stedolan.github.io/jq/'
license=('MIT')
depends=('glibc' 'oniguruma')
makedepends=('autoconf' 'automake' 'bison' 'flex' 'python3')
source=("https://github.com/jqlang/jq/releases/download/${pkgname}-${pkgver}/${pkgname}-${pkgver}.tar.gz")
sha512sums=('464861fb2e0d6934b616f1dc7f8002d7dae727c8c0c07b385b813e7522ba1ada8ead4165e1d99c892e3ea76e238c55a15b718c738805419721920f88f8d8478c')

build() {
    cd "${pkgname}-${pkgver}"
    ./configure --prefix=/usr
    make
}

package() {
    cd "${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" prefix=/usr install
    install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/COPYING"
}
