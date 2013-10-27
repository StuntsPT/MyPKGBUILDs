# Maintainer: Stunts <f.pinamartins@gmail.com>

pkgname=radeon-tray
_up_pkgname=Radeon-tray
pkgver=1.1
pkgrel=1
pkgdesc="A system tray icon for controlling radeon cards' power states"
arch=('any')
url="https://github.com/StuntsPT/Radeon-tray/"
license=('GPLv3')
depends=('python' 'python-pyqt4')
source=("https://github.com/StuntsPT/Radeon-tray/archive/v${pkgver}.tar.gz")
md5sums=('d1e3a06c6d96425fd59660525666cac6')

package() {
  cd ${srcdir}/${_up_pkgname}-${pkgver}
  yes | python3 setup.py install --root=${pkgdir}
  
  mkdir -p ${pkgdir}/usr/lib/systemd/system
  cp radeontray/systemd/radeonpm.service ${pkgdir}/usr/lib/systemd/system/

  mkdir -p ${pkgdir}/usr/share/applications
  cp radeontray/conf/radeontrayclient.desktop ${pkgdir}/usr/share/applications/

  mkdir -p  ${pkgdir}/usr/share/Radeon-tray-icon
  cp  radeontray/assets/radeon-tray.svg  ${pkgdir}/usr/share/Radeon-tray-icon
}
