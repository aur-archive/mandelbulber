# Maintainer: Wilfried Fauvel <wilfried.fauvel at gmail>
# Contributor: Martti Kühne <mysatyre at gmail dot com>

pkgname=mandelbulber
pkgver=1.21
pkgrel=2
pkgdesc='Easy to use, handy but experimental application designed to help you render 3D Mandelbrot fractals called Mandelbulb and some other kind of 3D fractals like Mandelbox, Bulbbox, Juliabulb, Menger Sponge.'
arch=('i686' 'x86_64')
url='http://sites.google.com/site/mandelbulber/'
license=('GPL')
depends=('gtk2' 'libjpeg-turbo' 'libpng')
makedepends=('make' 'gcc' 'pkg-config' 'patch' )
conflicts=('mandelbulber-svn')
source=("http://downloads.sourceforge.net/project/${pkgname}/${pkgname}${pkgver}-1.orig.tar.gz")
md5sums=('23d2f61fdb48ee4a9ebb737c5af586e8')

build() {

  # Applying patch
  #cd "${srcdir}/${pkgname}${pkgver}.orig"
  #echo "${srcdir}/${pkgname}${pkgver}"
  #patch -p0 -i $srcdir/mandelbulber1.19.patch

  cd "${srcdir}/${pkgname}${pkgver}-1.orig/makefiles"

  # Clean up pre-compiled binaries
  make clean

  # Build
  make all
}

package()
{
  # Install
  install -m755 -d "${pkgdir}/usr/bin"
  install -Dm755 "${srcdir}/${pkgname}${pkgver}-1.orig/makefiles/${pkgname}" \
                 "${pkgdir}/usr/bin/"
  install -m755 -d "${pkgdir}/usr/share/${pkgname}"
  mv -i "${srcdir}/${pkgname}${pkgver}-1.orig/usr/share/"* "${pkgdir}/usr/share/${pkgname}"
 }

