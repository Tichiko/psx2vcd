# Maintainer: Tichiko <tichikothedev@proton.me>


pkgname=psx2vcd-git
_pkgname=psx2vcd
pkgver=0.r4.g577313a
pkgrel=1
pkgdesc="Convert PS1 .bin/.cue to POPStarter .VCD with sane defaults and helpers"
arch=('any')
url="https://github.com/Tichiko/${_pkgname}"
license=('GPL3')
provides=("${_pkgname}")
conflicts=("${_pkgname}")
depends=(
'gawk'
'sed'
'psmisc'
'mame-tools' # chdman, etc, if used by the script
'popstationr-git' # AUR
'cue2pops' # AUR
)
makedepends=('git')
source=("${_pkgname}::git+${url}.git")
sha256sums=('SKIP')


pkgver() {
  cd "${srcdir}/${_pkgname}"
  # Prefer annotated tags; fall back to commit count + short hash
  if git describe --long --tags --match 'v*' >/dev/null 2>&1; then
    git describe --long --tags --match 'v*' \
    | sed 's/^v//; s/-/./g'
  else
    printf "0.r%s.g%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
  fi
}

package() {
  cd "${srcdir}/${_pkgname}"
  install -Dm755 "${_pkgname}" "${pkgdir}/usr/bin/${_pkgname}"
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  # If you add a man page later:
  # install -Dm644 man/${_pkgname}.1 "${pkgdir}/usr/share/man/man1/${_pkgname}.1"
}
