# Maintainer: kfgz <kfgz at interia dot pl>

pkgname=e-deklaracje
pkgrel=1
pkgver=7.0.3
pkgdesc="Program to tax settlements in Poland"
arch=('i686' 'x86_64')
url="http://www.finanse.mf.gov.pl/systemy-informatyczne/e-deklaracje"
license=(unknown)
[[ ${CARCH} = 'i686' ]] && depends=('adobe-air' 'acroread' 'acroread-fonts')
[[ ${CARCH} = 'x86_64' ]] && depends=('acroread' 'adobe-air' 'lib32-libxt' 'acroread-fonts')

makedepends=('unzip')
source=('e-deklaracje.air::http://www.finanse.mf.gov.pl/documents/766655/1196444/e-DeklaracjeDesktop.air' 'e-deklaracje.desktop')
noextract=(e-deklaracje.air)
md5sums=('e433684e9f15b16c425967d8bbe5289f'
         '2ba1cc559c57abe276b46f948a4c4265')

package() {
  unzip -q -u e-deklaracje.air
  install -D -m 644 "$srcdir/e-deklaracje.air" "$pkgdir/opt/$pkgname/$pkgname.air"
  install -D -m 644 "$srcdir/assets/icons/icon128.png" "$pkgdir/usr/share/pixmaps/$pkgname.png"
  install -D -m 644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
  install -D -m 755 "/usr/bin/adobe-air" "$pkgdir/opt/$pkgname/adobe-air_$pkgname"
  sed -i 's/-nodebug //' "$pkgdir/opt/$pkgname/adobe-air_$pkgname"
}