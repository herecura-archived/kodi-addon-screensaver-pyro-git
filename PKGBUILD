# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

_gitname=kodi-addon-screensaver-pyro
pkgname="$_gitname-git"
_commit=97e997e
pkgver=20170615.97e997e
pkgrel=1
pkgdesc="Pyro screensaver for Kodi"
arch=('i686' 'x86_64')
url='github.com/notspiff/screensaver.pyro'
license=('GPL')
groups=('kodi-git-addons' 'kodi-git-addons-screensaver')
depends=('kodi-git')
makedepends=('git' 'cmake' 'kodi-dev-git')
source=("$_gitname::git://github.com/notspiff/screensaver.pyro.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
	cd "$_gitname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
	cd "$_gitname"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
	cd "$_gitname"
	make DESTDIR="$pkgdir/" install
}

