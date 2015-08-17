# Mantainer: Diego Principe <cdprincipe@at@gmail@dot@com>

pkgname=qbittorrent-git-nogui
pkgver=3.1.0alpha_4500
pkgrel=1
pkgdesc="A bittorrent client written in C++ / Qt4 using the good libtorrent library, w/o gui"
arch=('i686' 'x86_64')
url="http://www.qbittorrent.org/"
license=('GPL')
depends=('libtorrent-rasterbar' 'qt4')
makedepends=('boost')
conflicts=('qbittorrent-nogui')
source=("git://github.com/qbittorrent/qBittorrent.git")
md5sums=('SKIP')

pkgver() {
  cd $srcdir/qBittorrent
#  echo $(cat ${srcdir}/qBittorrent/Changelog | grep v3 | cut -f4 -d'-')_$(git rev-list --count HEAD).$(git rev-parse --short HEAD)
  echo $(cat ${srcdir}/qBittorrent/version.pri | grep -o '[0-9]..*[0-9]*[a-z]')_$(git rev-list --count HEAD)
}

build() {
  cd $srcdir/qBittorrent
  ./configure --prefix=/usr --disable-gui
  make
}

package() {
  cd ${srcdir}/qBittorrent
  make INSTALL_ROOT=${pkgdir} install
}
