# Maintainer: David Becker <david dot becker at gmx dot org>

pkgname=flatlinerl
pkgver=1.0
pkgrel=2
pkgdesc="FlatlineRL was the entry in the 2013 7DRL competition by flend."
source=("http://flend.net/files/flatlinerl-v10-linux.zip")
md5sums=('51ca180de0dc48c34b56f64dbb2d16b9')
license=('unknown')
url="http://flend.net/flatlinerl/"
arch=('i686')
depends=('mono' 'sdl')

build() {
cat > flatlinerl << "EOF"
#!/bin/bash
cd /opt/flatlinerl
mono ./FlatlineRL.exe
EOF
}

package() {
install -dm775 "${pkgdir}/opt/flatlinerl"
chown :games "${pkgdir}/opt/flatlinerl"
install -dm757 "${pkgdir}/opt/flatlinerl/logs"
install -Dm755 "${srcdir}/flatlinerl-v10/FlatlineRL.exe" "${pkgdir}/opt/flatlinerl/FlatlineRL.exe"
install -Dm644 "${srcdir}/flatlinerl-v10/libtcod.so" "${pkgdir}/opt/flatlinerl/libtcod.so"
install -Dm644 "${srcdir}/flatlinerl-v10/libtcodWrapper.dll" "${pkgdir}/opt/flatlinerl/libtcodWrapper.dll"
install -Dm644 "${srcdir}/flatlinerl-v10/readme.txt" "${pkgdir}/opt/flatlinerl/readme.txt"
install -Dm644 "${srcdir}/flatlinerl-v10/tallfont.png" "${pkgdir}/opt/flatlinerl/tallfont.png"

install -d "${pkgdir}/usr/bin"
install -Dm755 "${srcdir}/flatlinerl" "${pkgdir}/usr/bin/"
}

