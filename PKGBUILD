pkgname="check_pacman"
pkgver="1.0.0"
pkgrel=1
epoch=0
pkgdesc="Checks for available updates using pacman"
arch=("any")
url="https://github.com/Donien/check_pacman"
license=("GPL")
groups=()
depends=()
makedepends=()
optdepends=(
    "fakeroot"
)
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=(
    "check_pacman"
)
noextract=()
sha256sums=(
    "6b6a526313dddefae5193f87f6ea9090c257f4f45a21fbbf7e27932779b8bd3f"
)


package() {
    mkdir -p "${pkgdir}/usr/lib/monitoring-plugins/"
    install -m755 "${srcdir}/check_pacman" "${pkgdir}/usr/lib/monitoring-plugins/check_pacman"
}
