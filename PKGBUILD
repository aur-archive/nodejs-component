# Maintainer: Micha Alt <micha.tucker at gmail dot com>

_npmname=component
pkgname=nodejs-$_npmname
pkgver=1.1.0
pkgrel=3
pkgdesc="frontend package manager and build tool for modular web applications"
arch=('any')
url="https://github.com/componentjs/component"
license=('MIT')
depends=('nodejs')
makedepends=('npm')
source=(https://registry.npmjs.org/$_npmname/-/$_npmname-$pkgver.tgz
       'LICENSE')
noextract=($_npmname-$pkgver.tgz)
md5sums=('1b9c9ef770de3d2194ef3fb4fc7702d9'
         'ac0e81178f963a3f51a1fd864a773b5e')

package() {
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  cd "$srcdir"
  local _npmdir="$pkgdir/usr/lib/node_modules/"
  mkdir -p "$_npmdir"
  cd "$_npmdir"
  npm install --user root -g --prefix "$pkgdir/usr" $_npmname@$pkgver
}
