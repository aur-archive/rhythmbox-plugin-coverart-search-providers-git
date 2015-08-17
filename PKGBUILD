# Maintainer: Zhengyu Xu <xzy3186[at]gmail[dot]com>
pkgname=rhythmbox-plugin-coverart-search-providers-git
_gitname="coverart-search-providers"
pkgver=v1.1.1.gcd28358
pkgrel=1
pkgdesc="Drop in Rhythmbox replacement for the default CoverArt Search plugin"
url="https://github.com/fossfreedom/coverart-search-providers"
arch=('x86_64' 'i686')
license=('GPLv3')
depends=('glib2' 'gtk3' 'python-lxml' 'python-chardet' 'python-pillow' 'rhythmbox' 'python-mako' 'python-mutagen' 'python-requests')
conflicts=('rhythmbox-plugin-coverart-search-providers')
provides=('rhythmbox-plugin-coverart-search-providers')
makedepends=('git')
source="git://github.com/fossfreedom/coverart-search-providers.git"
md5sums=('SKIP')
install=$pkgname.install

pkgver() {
  cd "$srcdir/$_gitname"
  git describe --always | sed 's|-|.|g'
}

package() {
  cd "${srcdir}/$_gitname"
  ############# fix crash bugs ################
  #sed -i "s/self.entry_changed_id/#self.entry_changed_id/g" coverart_album.py
  sed -i "s/Loader=python$/Loader=python3/g" coverart_search_providers.plugin

  make DESTDIR=${pkgdir} install
}

# vim:set ts=2 sw=2 et:
