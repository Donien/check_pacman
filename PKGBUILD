pkgname="check_pacman"
pkgver="1.0.1"
pkgrel=1
epoch=0
pkgdesc="Checks for available updates using pacman"
arch=("any")
url="https://github.com/Donien/check_pacman"
license=("GPL-3.0-or-later")
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
    "46a407208022eee3e04989ce728ee87bd6e4bdaec2930db015df4c7331824d17"
)


package() {
    mkdir -p "${pkgdir}/usr/lib/monitoring-plugins/"
    install -m755 "${srcdir}/check_pacman" "${pkgdir}/usr/lib/monitoring-plugins/check_pacman"
}
