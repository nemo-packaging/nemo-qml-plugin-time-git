## $Id$
# Maintainer: TheKit <nekit1000 at gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=nemo-qml-plugin-time-git
pkgver=0.1.3.r0.ge9ac208
pkgrel=1
pkgdesc="Wall clock plugin for Nemo Mobile"
arch=('x86_64' 'aarch64')
url="https://git.sailfishos.org/mer-core/nemo-qml-plugin-time"
license=('BSD')
depends=('qt5-base' 'nemo-qml-plugin-dbus')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://git.sailfishos.org/mer-core/nemo-qml-plugin-time.git')
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/${pkgname%-git}"
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

prepare() {
    cd "$srcdir/${pkgname%-git}"
}

build() {
    cd "$srcdir/${pkgname%-git}"
    qmake
    make
}

package() {
    cd "$srcdir/${pkgname%-git}"
    make INSTALL_ROOT="$pkgdir/" install
    cd "$pkgdir"
    rm -rf opt
}
