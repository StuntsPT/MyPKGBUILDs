# Maintainer: Stunts <f.pinamartins@gmail.com>
# Contributor: damir <damir@archlinux.org>

pkgname=biopython
pkgver=1.60
pkgrel=1
pkgdesc="Freely available Python tools for computational molecular biology"
arch=('i686' 'x86_64')
url="http://www.biopython.org"
license=('custom')
depends=('glibc' 'python2' 'python2-numpy')
source=(http://www.biopython.org/DIST/${pkgname}-${pkgver}.tar.gz)
md5sums=('8539f1761483187a04da9bf7f499a21f')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  yes | python2 setup.py build
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  yes | python2 setup.py install --root="${pkgdir}"
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
