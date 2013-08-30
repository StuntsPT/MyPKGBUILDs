# Maintainer: Stunts <f.pinamartins@gmail.com>
# Contributor: damir <damir@archlinux.org>

pkgname=python2-biopython
_upstream_pkgname=biopython
pkgver=1.62
pkgrel=1
pkgdesc="Freely available Python tools for computational molecular biology"
arch=('i686' 'x86_64')
url="http://www.biopython.org"
license=('custom')
depends=('glibc' 'python2' 'python2-numpy')
source=(http://www.biopython.org/DIST/${_upstream_pkgname}-${pkgver}.tar.gz)
md5sums=('4deca9b640b8347c5eb202df7dbb65f9')

build() {
  cd "${srcdir}/${_upstream_pkgname}-${pkgver}"
  yes | python2 setup.py build
}

package() {
  cd "${srcdir}/${_upstream_pkgname}-${pkgver}"
  yes | python2 setup.py install --root="${pkgdir}"
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${_upstream_pkgname}/LICENSE"
}
