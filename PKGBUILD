# Maintainer: Philip Lorenz <lorenzph@users.sourceforge.net>
pkgname=python-poppler-qt
_realpkgname=python-poppler-qt4
pkgver=0.18.1
pkgrel=1
pkgdesc="A Python 3 binding to poppler-qt"
arch=('i686' 'x86_64')
url="https://github.com/wbsoft/python-poppler-qt4"
license=('LGPL')
depends=(python-pyqt4 poppler-qt4 python)
source=(https://github.com/wbsoft/$_realpkgname/archive/v$pkgver.tar.gz
        Support-PyQt-s-new-build-system.patch)

md5sums=('e877fcd00180a817bdcbae1b3ecc37c5'
         '15d90c80b5dc32befbf9c022f9736417')

prepare() {
  cd "$srcdir/$_realpkgname-$pkgver"
  patch -p1 -i "$srcdir/Support-PyQt-s-new-build-system.patch"
}

build() {
  cd "$srcdir/$_realpkgname-$pkgver"

  python setup.py build_ext --qmake-bin="$(which qmake-qt4)"
}

package() {
  cd "$srcdir/$_realpkgname-$pkgver"

  python setup.py install --root="${pkgdir}" build_ext --qmake-bin="$(which qmake-qt4)"
}

# vim:set ts=2 sw=2 et:
