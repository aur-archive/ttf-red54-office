# Maintainer: 謝致邦 <Yeking@Red54.com>

pkgname=ttf-red54-office
pkgver=2013
pkgrel=1
pkgdesc='Microsoft Office TrueType fonts'
arch=('any')
url='http://msdn.microsoft.com/en-us/evalcenter/jj720319.aspx'
license=('custom')
depends=('fontconfig' 'xorg-fonts-encodings' 'xorg-mkfontscale' 'xorg-mkfontdir')
makedepends=('cabextract')
provides=('ttf-font')
install="$pkgname.install"
source=(
http://care.dlservice.microsoft.com/dl/download/2/9/C/29CC45EF-4CDA-4710-9FB3-1489786570A1/OfficeProfessionalPlus_x86_en-us.img
)
md5sums=('78da86c934cbd510d5cada8f54d02a5b')
PKGEXT='.pkg.tar'

build() {
  cd $srcdir
  cabextract -LF mtextra.ttf_1033 -d fonts office.en-us/officelr.cab
  cabextract -LF wingdng*.ttf -d fonts proplusr.ww/proprww2.cab
}

package() {
  cd $srcdir/fonts
  mv mtextra.ttf_1033 mtextra.ttf
  install -dm755 $pkgdir/usr/share/fonts/office
  install -m644 * $pkgdir/usr/share/fonts/office
}
