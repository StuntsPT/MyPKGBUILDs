# Maintainer: Stunts <f.pinamartins@gmail.com>

_basename=rtl8723au
pkgname=${_basename}-git
pkgver=a1c3032
pkgrel=1
pkgdesc="Kernel driver for rtl8723au based wireless cards"
url="https://github.com/lwfinger/rtl8723au"
arch=('any')
license=('GPL')
makedepends=('linux-headers' 'git')
#install="${pkgname}.install"


source=("${_basename}::git+https://github.com/lwfinger/${_basename}.git")
sha256sums=('SKIP')

pkgver() {
    cd "${_basename}"
	git describe --always | sed 's|-|.|g'
}


build() {
    cd "${srcdir}/${_basename}"
	make
}

package() {
	cd "${srcdir}/${_basename}"
 	install -D -m 644 8723au.ko \
    "${pkgdir}/usr/lib/modules/${_extramodules}/8723au.ko"
}

