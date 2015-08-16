pkgname=lazarus-cross-x86_64-win64
pkgver=0.9.30.2
pkgrel=1
pkgdesc='Delphi-like IDE for FreePascal (win64 crosscompiler)'
url='http://www.lazarus.freepascal.org/'
license=('GPL2' 'MPL' 'custom:LGPL')
arch=(any)
depends=('fpc' 'fpc-src' 'gtk2' 'fpc-cross-x86_64-win64' 'lazarus')
options=('!emptydirs' '!makeflags')
source=(http://downloads.sourceforge.net/project/lazarus/Lazarus%20Zip%20_%20GZip/Lazarus%20$pkgver/lazarus-$pkgver-src.tar.bz2)
md5sums=('0dcf54613c2f9d38a32d183431e2dfc9')

build() {
  cd $srcdir/lazarus
  make FPC=/usr/bin/fpc clean lcl packager/registration ideintf packager components OS_TARGET=win64 CPU_TARGET=x86_64
}

package() {
  cd $srcdir/lazarus
  
  # skip the 'make install' mess completely and do everything manually
  mkdir -p $pkgdir/usr/lib/lazarus
  find . -type f -path *x86_64-win64* -exec cp --parents '{}' $pkgdir/usr/lib/lazarus/ \;
}

