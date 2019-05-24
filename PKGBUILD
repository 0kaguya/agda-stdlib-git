pkgname=agda-stdlib-git
pkgver=*
pkgrel=1
pkgdesc="The Agda standard library"
arch=('x86_64')
url="https://github.com/agda/agda-stdlib"
license=('custom')
makedepends=('git')
provides=('agda-stdlib')
conflicts=('agda-stdlib')
source=("agda-stdlib::git+https://github.com/agda/agda-stdlib.git")
md5sums=('SKIP')

pkgver() {
    cd "$srcdir/${pkgname%-git}"
    git describe --long --tags | sed 's/^v//;s/-/.r/;s/-/./'
}

build() {
    cd "$srcdir/${pkgname%-git}"

    for file in `find "src/" -name "*.agda"`
    do
        if [ ! -f $file"i" ]; then agda $file; fi
    done
}

package() {
    cd "$srcdir/${pkgname%-git}"

    lib="$pkgdir/usr/share/agda/lib"
    install -D -m644 "standard-library.agda-lib" "$lib/standard-library.agda-lib"
    cp -r "src" "$lib"; chmod -R 644 "$lib/src"; chmod -R +X "$lib/src"

    install -D -m644 "LICENCE" "$pkgdir/usr/share/licenses/${pkgname%-git}/LICENCE"
}
