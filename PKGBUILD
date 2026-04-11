# Maintainer: Tapas <tapas@pratibmb.com>
pkgname=pratibmb-bin
pkgver=0.2.0
pkgrel=1
pkgdesc="Chat with your 10-years-younger self. 100% local, no cloud, no telemetry"
arch=('x86_64')
url="https://pratibmb.com"
license=('AGPL-3.0-or-later')
depends=('python>=3.10' 'fuse2')
provides=('pratibmb')
conflicts=('pratibmb')
options=('!strip')
source=("pratibmb-bin-${pkgver}.AppImage::https://github.com/tapaskar/Pratibmb/releases/latest/download/Pratibmb_${pkgver}_amd64.AppImage"
        "pratibmb.desktop")
sha256sums=('bcb825b386ef73f1576937b8063667c800d9016a46ffea7f1be340fa6f83cb9b'
            'SKIP')

prepare() {
    chmod +x "${srcdir}/${pkgname}-${pkgver}.AppImage"
}

package() {
    install -Dm755 "${srcdir}/${pkgname}-${pkgver}.AppImage" "${pkgdir}/opt/pratibmb/pratibmb.AppImage"
    install -Dm644 "${srcdir}/pratibmb.desktop" "${pkgdir}/usr/share/applications/pratibmb.desktop"

    # Create symlink in PATH
    install -dm755 "${pkgdir}/usr/bin"
    ln -s /opt/pratibmb/pratibmb.AppImage "${pkgdir}/usr/bin/pratibmb"
}
