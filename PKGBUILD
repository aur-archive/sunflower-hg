pkgname=sunflower-hg
pkgver=2059.24f23ee1ae59
pkgrel=1
pkgdesc="Small and highly customizable twin-panel file manager for Linux with support for plugins"
arch=('any')
url="https://code.google.com/p/sunflower-fm/"
license=('GPL3')
depends=('pygtk' 'librsvg')
makedepends=('mercurial')
optdepends=('python2-notify' 'vte')
conflicts=('sunflower')
source=('hg+https://sunflower-fm.googlecode.com/hg/'
	'sunflower.desktop')
md5sums=('SKIP'
	 '9cfbe8c2075b39b9d62242ef48598105')
pkgver() {
  cd hg
  echo $(hg identify -n).$(hg identify -i)
}
package() {
    mkdir -p $pkgdir/{opt,usr/bin}
    cp -a $srcdir/hg $pkgdir/opt/sunflower
    echo -e '#!/bin/sh\npython2 /opt/sunflower/Sunflower.py "$@"' > $pkgdir/usr/bin/sunflower
    chmod +x $pkgdir/usr/bin/sunflower
    mkdir -p $pkgdir/usr/share/applications
    cp sunflower.desktop $pkgdir/usr/share/applications/
}
