# Maintainer:   Lucky <archlinux@builds.lucky.li>

pkgname=vzstats-git
_pkgname="${pkgname%-*}"
pkgver=0.5.3
pkgrel=1
pkgdesc="OpenVZ stats collection daemon"
url="https://openvz.org/Vzstats"
license=("GPL")
arch=("any")
makedepends=("git")
conflicts=("${_pkgname}")
provides=("${_pkgname}")
source=("git://git.openvz.org/pub/${_pkgname}")
md5sums=("SKIP")

pkgver() {
  cd "${_pkgname}"
  git describe --always | sed "s|^${_pkgname}-||g;s|-|.|g"
}

build() {
  cd "${srcdir}/${_pkgname}"

  make
}

package() {
  cd "${srcdir}/${_pkgname}"

  make DESTDIR="${pkgdir}" \
    SBINDIR="/usr/bin" \
    install #install-cronjob
}
