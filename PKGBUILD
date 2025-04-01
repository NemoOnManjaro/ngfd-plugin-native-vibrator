# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

_basename=ngfd-plugin-droid-vibrator
pkgname=ngfd-plugin-native-vibrator

pkgver=1.4.1
pkgrel=1
pkgdesc="Vibrator native plugin for ngfd"
arch=('x86_64' 'aarch64')
url="https://github.com/mer-hybris/ngfd-plugin-droid-vibrator"
license=('LGPL-2.1')
depends=('ngfd')
makedepends=('cmake' 'glib2')
conflicts=("ngfd-plugin-droid-vibrator")
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('ce87c358cbdc70898017ba5407de800c2b6fe1d7768f4b25f82e70e0f02f426b')

build() {
    cd $_basename-$pkgver
    cmake \
        -DCMAKE_INSTALL_PREFIX:PATH='/usr' \
        -DNATIVE_VIBRATOR=ON . \
        -DCMAKE_POLICY_VERSION_MINIMUM=3.5
    make  all
}

package() {
    cd $_basename-$pkgver
    make DESTDIR="$pkgdir" install
}
