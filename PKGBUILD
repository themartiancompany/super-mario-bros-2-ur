# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2024, 2025  Pellegrino Prevete
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

# Maintainer:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
# Maintainer:
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_os="$( \
  uname \
    -o)"
_evmfs_available="$( \
  command \
    -v \
    "evmfs" || \
    true)"
if [[ ! -v "_evmfs" ]]; then
  if [[ "${_evmfs_available}" != "" ]]; then
    _evmfs="true"
  elif [[ "${_evmfs_available}" == "" ]]; then
    _evmfs="false"
  fi
fi
if [[ "${_evmfs}" == "true" ]]; then
  _archive="false"
elif [[ "${_evmfs}" == "true" ]]; then
  _archive="true"
fi
if [[ ! -v "_dl_agent" ]]; then
  _dl_agent="true"
fi
if [[ ! -v "_retroarch" ]]; then
  if [[ "${_os}" == "Android" ]]; then
    _retroarch="true"
  elif [[ "${_os}" == "GNU/Linux" ]]; then
    _retroarch="false"
  fi
fi
if [[ ! -v "_fceux" ]]; then
  if [[ "${_os}" == "Android" ]]; then
    _fceux="false"
  elif [[ "${_os}" == "GNU/Linux" ]]; then
    _fceux="true"
  fi
fi
_zpaq_archiver="lrzip"
_emulators=()
if [[ "${_retroarch}" == "true" ]]; then
  _emulator="retroarch"
  _emulators+=(
    "${_emulator}"
  )
fi
if [[ "${_fceux}" == "true" ]]; then
  _emulator="fceux"
  _emulators+=(
    "${_emulator}"
  )
fi
_app_id="com.nintendo.SuperMarioBros"
_uuid="NES-NROM-256-01"
_title="Super Mario Bros"
_rom_filename=""
_pkg=super-mario-bros
pkgname="${_pkg}"
pkgver=1.0
pkgrel=1
_pkgdesc=(
  "Platform game developed and"
  "published in 1985 by Nintendo"
  "for the Famicom in Japan and"
  "for the Nintendo Entertainment"
  "System (NES) in North America."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'any'
)
url="https://en.wikipedia.org/wiki/${_title}"
depends=(
  "${_emulators[@]}"
  "videogame-launcher"
)
if [[ "${_retroarch}" == "true" ]]; then
  depends+=(
    "libretro-quicknes"
  )
fi
makedepends=()
if [[ "${_os}" == "Android" ]]; then
  makedepends+=(
    "termux-shortcuts-utils"
  )
fi
_archive="https://archive.org"
_wikimedia="https://upload.wikimedia.org"
license=(
  "custom"
)
_dmca_exemption="${_archive}/about/dmca.php"
_archive_namespace="download/nes-roms"
_archive_rom_url="${_archive}${_archive_namespace}/Super%20Mario%20Bros.%20%28World%29.nes"
_wikimedia_namespace="wikipedia/en"
# EVMFS configuration
# that kid address
_namespace="0x926acb6aA4790ff678848A9F1C59E578B148C786"
_evmfs_rom_sum="684feefca60a36aa4d1a455ab8db17d8ecf1bb840fc92505f7ed6e6d5357c46b"
_evmfs_rom_sig_sum="7871474a3ad49f033d880fa78b0b5771b15df71a47b29bc3d63167aed3478890"
_pic_sum="2b7b72fe313c3c544c58d718b9f8f9abea957091c0070ba233234c7e4d0f0a95"
# testnets
# gensyn
_network="685685"
# lens
_network="37111"
# monad
_network="10143"
# polygon amoy
_network="80002"
# holesky
_network="17000"
# aeneid
_network="1315"
# zetachain
_network="7001"
# chiado
_network="10200"
# sepolia
_network="11155111"
# mainnets
# dogechain
_network="2000"
# kucoin community chain
_network="321"
# polygon
_network="137"
# binance smart chain
_network="56"
# gnosis
_network="100"
_pic_network="${_network}"
# ethereum
_network="1"
# File system addresses
_fs=(
  ["62831"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["555666"]="0x629d369Edd5f64391f0bA6187F2794D7b54F7e57"
  ["37111"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["10143"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["80002"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["10200"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["11155111"]="0x151920938488F193735e83e052368cD41F9d9362"
  ["63"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["685685"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["43113"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["17000"]="0x151920938488F193735e83e052368cD41F9d9362"
  ["1315"]="0x151920938488F193735e83e052368cD41F9d9362"
  ["7001"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["2000"]="0xDebB1F4A3dD682BD131ba90aA45aC4735FbaF9D0"
  ["321"]="0x78BF4B05035BDBEeE1C2048920e85bBA424be188"
  ["137"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["56"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["1666600000"]="0x1f762a05cfab651d3d95778f9c89c46545913623"
  ["100"]="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
  ["1"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
)
_file_system="${_fs["${_network}"]}"
_evmfs_rom_uri="evmfs://${_network}/${_file_system}/${_namespace}/${_evmfs_rom_sum}"
_evmfs_pic_uri="evmfs://${_pic_network}/${_file_system}/${_namespace}/${_pic_sum}"
source=(
  "nes-template.desktop"
  "launcher"
)
sha256sums=(
  "593e726db737390c7cd41e28a570d2ab19a3383d9ae163171a1afc14acaa6019"
  "b25117ba185a5af887b1e14fe8698a4de946475d17998637a88b5c06b58fde44"
)
if [[ "${_archive}" == "true" ]]; then
  _rom="${_app_id}.nes::${_archive_rom_uri}"
  _rom_sum="0b3d9e1f01ed1668205bab34d6c82b0e281456e137352e4f36a9b2cfa3b66dea"
  # This one could change actually because Wikipedia users can update
  # this and they have to delete the previous version.
  # So you know, another reason to use the evmfs as default.
  _pic_uri="${_wikimedia}/${_wikimedia_namespace}/0/03/Super_Mario_Bros._box.png"
  _dl_agent="true"
elif [[ "${_evmfs}" == "true" ]]; then
  makedepends+=(
    "evmfs"
    "${_zpaq_archiver}"
  )
  if [[ ! " ${DLAGENTS[*]} " == *" evmfs::"* ]]; then
    _msg=(
      "No download agent configured to manage"
      "Ethereum Virtual Machine File System"
      "resources (evmfs://<uri>). The download"
      "will happen in the 'prepare' function."
    )
    msg \
      "${_msg[*]}"
    _dl_agent="false"
  fi
  _rom="${_app_id}.nes.zpaq::${_evmfs_rom_uri}"
  _rom_sum="${_evmfs_rom_sum}"
  _pic_uri="${_evmfs_pic_uri}"
fi
if [[ "${_dl_agent}" == "true" ]]; then
  source+=(
    "${_rom}"
    "${_app_id}.png::${_pic_uri}"
  )
  sha256sums+=(
    "${_rom_sum}"
    "${_pic_sum}"
  )
fi

_desktop_file_prepare() {
  msg \
    "Preparing desktop file."
  mv \
    "nes-template.desktop" \
    "${_app_id}.desktop"
  sed \
    -i \
    "s/%_title%/${_title}/g" \
    "${_app_id}.desktop"
  sed \
    -i \
    "s/%pkgdesc%/${pkgdesc}/g" \
    "${_app_id}.desktop"
  sed \
    -i \
    "s/%_app_id%/${_app_id}/g" \
    "${_app_id}.desktop"
  sed \
    -i "s/%_uuid%/${_uuid}/g" \
    "${_app_id}.desktop"
  sed \
    -i \
    "s/%_game_launcher%/${_emulator}/g" \
    "${_app_id}.desktop"
  sed \
    -i \
    "s/%_game_language%/any/g" \
    "${_app_id}.desktop"
  msg \
    "done"
}

_launcher_prepare() {
  msg \
    "Preparing command-line launcher."
  mv \
    "launcher" \
    "${pkgname}"
  sed \
    -i \
    "s/%_app_id%/${_app_id}/g" \
    "${pkgname}"
  sed \
    -i \
    "s/%_game_launcher%/${_emulator}/g" \
    "${pkgname}"
  sed \
    -i \
    "s/%_game_language%/any/g" \
    "${pkgname}"
  sed \
    -i \
    "s/%_game_platform%/nes/g" \
    "${pkgname}"
  msg \
    "Done."
}

_usr_get() {
  local \
    _bin
  _bin="$( \
    dirname \
      "$(command \
           -v \
	   "env")")"
  dirname \
    "${_bin}"
}

_file_checksum() {
  local \
    _file="${1}" \
    _sum_correct="${2}" \
    _sum
  _checksum_flag="false"
  _sum="$( \
    sha256sum \
      "${_file}" | \
        awk \
          '{print $1}')"
  _msg=(
    "Local file '${_file}' sum: '${_sum}'"
  )
  msg \
    "${_msg[*]}"
  if [[ "${_sum}" == "${_sum_correct}" ]]; then
    _msg=(
      "Local file '$( \
        realpath \
          "${_file}")'"
      "has correct sum."
    )
    msg \
      "${_msg[*]}"
    _checksum_flag="true"
  elif [[ "${_sum}" != "${_rom_sum}" ]]; then
    _msg=(
      "Local file '${_file}' sum: '${_sum}'"
      "different from expected '${_rom_sum}'."
    )
    msg \
      "${_msg[*]}"
  fi
}

_evmfs_get() {
  local \
    _file="${1}" \
    _sum="${2}" \
    _uri="${3}" \
    _download \
    _checksum_flag
  _download="false"
  if [[ ! -e "${_file}" ]]; then
    _msg=(
      "File '${_file}'"
      "not found, downloading."
    )
    msg \
      "${_msg[*]}"
    _download="true"
  else
    _file_checksum \
      "${_file}" \
      "${_sum}"
    if [[ "${_checksum_flag}" == "false" ]]; then
      _download="true"
    fi
  fi
  if [[ "${_download}" == "true" ]]; then
    _msg=(
      "Downloading file '${_file}' from EVMFS"
      "uri '${_uri}'."
    )
    msg \
      "${_msg[*]}"
    evmfs \
      -v \
      -o \
        "${_file}" \
      get \
        "${_uri}"
  fi
}

_rom_extract() {
  lrunzip \
    -z \
    --outfile "${_app_id}.nes" -- \
    "${_app_id}.nes.zpaq"
}

prepare() {
  local \
    _sum \
    _download \
    _extract
  _download="false"
  _extract="false"
  if [[ "${_dl_agent}" == "false" ]]; then
    _evmfs_get \
      "${_app_id}.nes.zpaq" \
      "${_rom_sum}" \
      "${_evmfs_rom_uri}"
    _evmfs_get \
      "${_app_id}.png" \
      "${_pic_sum}" \
      "${_evmfs_pic_uri}"
  fi
  if [[ ! -e "${_app_id}.nes" ]]; then
    _extract="true"
  fi
  if [[ "${_extract}" == "true" ]]; then
    _rom_extract
  fi
  _desktop_file_prepare
  _launcher_prepare
}

_pkgdir_get() {
  local \
    _pkgdir="${1}"
  realpath \
    "${_pkgdir}/../../../.."
}

package() {
  local \
    _game_dir \
    _rom_dir \
    _rom_install_dir
  _game_dir="/usr/games/${_app_id}"
  install \
    -vdm755 \
    "${pkgdir}${_game_dir}"
  if [[ "${_os}" == "GNU/Linux" ]]; then
    _rom_dir="${_game_dir}"
    _rom_install_dir="${pkgdir}${_rom_dir}"
  elif [[ "${_os}" == "Android" ]]; then
    _rom_dir="/storage/emulated/0/Android/media/${_app_id}"
    _rom_install_dir="$( \
      _pkgdir_get \
        "${pkgdir}")${_rom_dir}"
    ln \
      -s \
      "${_rom_dir}/${_uuid}.nes" \
      "${pkgdir}${_game_dir}/${_uuid}.nes"
  fi
  install \
    -vDm644 \
    "${_app_id}.nes" \
    "${_rom_install_dir}/${_uuid}.nes"
  echo \
    "${_rom_dir}/${_uuid}.nes" > \
    "${pkgdir}${_game_dir}/any"
  install \
    -vDm755 \
    "${_app_id}.desktop" \
    "${pkgdir}/usr/share/applications/${_app_id}.desktop"
  install \
    -vDm644 \
    "${_app_id}.png" \
    "${pkgdir}/usr/share/icons/${_app_id}-${_uuid}.png"
  if [[ "${_os}" == "Android" ]]; then
    install \
      -vdm755 \
      "${pkgdir}/home/.shortcuts"
    termux-shortcut-new \
      -o \
        "${pkgdir}/home/.shortcuts" \
      "${_app_id}.desktop"
    install \
      -vDm644 \
      "${_app_id}.png" \
      "${pkgdir}/home/.shortcuts/icons/${_title}.png"
  fi
  install \
    -vDm755 \
    "${pkgname}" \
    "${pkgdir}/usr/bin/${pkgname}"
}

# vim:set sw=2 sts=-1 et:
