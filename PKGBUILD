# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Truocolo <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
# Maintainer: Pellegrino Prevete (dvorak) <pellegrinoprevete@gmail.com>
# Maintainer: Pellegrino Prevete (dvorak) <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_os="$( \
  uname \
    -o)"
_evmfs="true"
_pkg="mame2000"
_pkgname="libretro-${_pkg}"
_Pkg="MAME2000"
pkgname="${_pkgname}-bin"
pkgver="0.37b5"
pkgrel=1
_pkgdesc=(
  "RetroArch backend for"
  "the 2000 version of MAME"
  "multi-purpose"
  "emulation framework."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'arm'
  'armv7l'
)
_http="https://github.com"
_ns="libretro"
url="${_http}/${_ns}/${_pkg}-libretro"
license=(
  'custom:MAME License'
)
depends=(
  'retroarch'
)
if [[ "${_os}" != "GNU/Linux" ]] && \
   [[ "${_os}" == "Android" ]]; then
  depends+=(
    'inteppacman'
  )
fi
optdepends=(
)
[[ "${_os}" != "GNU/Linux" ]] && \
[[ "${_os}" == "Android" ]] && \
  optdepends+=(
  )
makedepends=(
  'coreutils'
  'evmfs'
)
checkdepends=(
)
provides=(
  "${_pkgname}=${pkgver}"
)
conflicts=(
  "${_pkgname}"
)
source=()
sha256sums=()
_lib="${_pkg}_libretro_android.so"
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
_lib_sum="66db7a0b724d48b604f6fb8cb087d934b67a5c98d34e7d85c50bc76b6099c329"
_evmfs_uri="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}/${_lib_sum}"
_lib_src="${_lib}.tar.xz::${_evmfs_uri}"
source+=(
  "${_lib_src}"
)
sha256sums+=(
  "${_lib_sum}"
)

validgpgkeys=(
)

package() {
  local \
    _dest_dir
  _dest_dir="/data/data/com.retroarch/cores"
  install \
    -dm755 \
    "${pkgdir}${_dest_dir}"
  install \
    -Dm644 \
    "${srcdir}/${_lib}" \
    "${pkgdir}/${_dest_dir}/${_lib}"
}

# vim: ft=sh syn=sh et
