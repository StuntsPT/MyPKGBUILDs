# Maintainer: Stunts <f.pinamartins@gmail.com>

pkgname=beagle-lib
pkgver=1082
pkgrel=2
pkgdesc="A general purpose library for evaluating the likelihood of sequence evolution on trees."
arch=('i686' 'x86_64')
url="http://code.google.com/p/beagle-lib/"
license=('LGPL')
depends=('libltdl')
optdepends=('cuda-toolkit: for doing calculations on the GPU' 'openjdk6: for usage with BEAST')
makedepends=('svn')

_svntrunk="http://beagle-lib.googlecode.com/svn/trunk/"
_svnmod="beagle-lib"

#Beagle won't support being built with multiple cores!!
unset MAKEFLAGS

build() {
  msg "Starting SVN checkout..."
  cd ${srcdir}
    if [ -d $_svnmod/.svn ]; then
      (cd $_svnmod && svn up -r $pkgver)
    else
      svn co $_svntrunk --config-dir ./ -r $pkgver $_svnmod
    fi
  msg "SVN checkout done or server timeout"

  msg "Creating build copy..."
  if [ -d ${srcdir}/$_svnmod-build ]; then
    rm -rf $_svnmod-build
  fi

  cp -r $_svnmod $_svnmod-build
  cd $_svnmod-build
  ./autogen.sh
  ./configure --with-cuda=/opt/cuda-toolkit/ --prefix=/usr
  make
}

package() {
    cd $_svnmod-build
    make DESTDIR=${pkgdir} install
}
