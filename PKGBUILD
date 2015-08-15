# Maintainer: skydrome <skydrome@i2pmail.org>

pkgname=ejre
_major=7
_minor=60

epoch=1
pkgver="${_major}.u${_minor}"
pkgrel=3

pkgdesc="Java SE Embedded Runtime Environment $_major"
arch=('i686' 'arm' 'armv6h' 'armv7h')
url="http://www.oracle.com/technetwork/java/embedded/embedded-se/downloads/index.html"
license=('custom')
depends=('java-common' 'ca-certificates-java')
provides=("java-runtime=$_major" "java-runtime-headless=$_major" "java-runtime-embedded=$_major" "java-runtime-headless-embedded=$_major")
options=(!strip)
install='jre.install'

case "$CARCH" in
      i686) _branch='x86' ; md5sums=('d40b70ad9d479c967453eab363709f27') ;;
    armv?h) _branch='arm' ; md5sums=('ad10f4ea6be0a43701b7ceafcc96c2be') ;;
       arm) _branch='arm5'; md5sums=('933d489cc6ea9fe9d686a619d4a2f4c3') ;;
esac
source=("https://github.com/skydrome/ejre/archive/${_branch}.zip")

package() {
    cd "$srcdir/ejre-${_branch}/ejre1.${_major}.0_${_minor}"
    mkdir -p "$pkgdir"/usr/{share/licenses/java7-embedded,lib/jvm/java-7-embedded/jre}

    cp -r COPYRIGHT *.txt "$pkgdir/usr/share/licenses/java7-embedded/"
    cp -ra *              "$pkgdir/usr/lib/jvm/java-7-embedded/jre/"
}
