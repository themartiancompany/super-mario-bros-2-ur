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
if [[ ! -v "_langs" ]]; then
  _langs=()
fi
if [[ ! -v "_famicom" ]]; then
  _famicom="true"
fi
if [[ ! -v "_nes" ]]; then
  _nes="true"
fi
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
_xz_archiver="lrzip"
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
if [[ ! -v "_langs" ]]; then
  _langs=()
fi
_app_id="com.nintendo.SuperMarioBros2"
_uuid_ja="FMC-SMB"
_uuid_en="${_uuid_ja}"
_game_title="Super Mario Bros. 2"
_rom_filename=""
_pkg=super-mario-bros-2
pkgbase="${_pkg}"
pkgname=()
if [[ "${_famicom}" == "true" ]]; then
  _langs+=(
    "ja"
    "en"
  )
  pkgname+=(
    "${_pkg}-famicom"
  )
fi
if [[ "${_nes}" == "true" ]]; then
  _langs+=(
    "en"
  )
  pkgname+=(
    "${_pkg}-nes"
  )
fi
pkgver=1.0
_videogame_launcher_pkgver="0.0.0.0.0.0.0.0.0.0.1.1"
pkgrel=1
_pkgdesc=(
  "1986 platform game developed"
  "by Nintendo R&D4 for the"
  "FamiCom Disk System (FDS)."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'any'
)
url="https://en.wikipedia.org/wiki/${_game_title}"
depends=(
  "${_emulators[@]}"
  "videogame-launcher>=${_videogame_launcher_pkgver}"
)
if [[ "${_fceux}" == "true" ]]; then
  depends+=(
    "famicom-bios"
  )
fi
if [[ "${_retroarch}" == "true" ]]; then
  depends+=(
    "libretro-quicknes"
  )
fi
makedepends=(
  "coreutils"
  "videogame-launcher>=${_videogame_launcher_pkgver}"
)
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
# EVMFS configuration
# that kid address
_ns="0x926acb6aA4790ff678848A9F1C59E578B148C786"
# Dvorak
_sig_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
_famicom_sum="30a2dec2df341c418bf6608569dc24b8cff7c4dfe18e3f71ef43dc1e708322ff"
_famicom_sig_sum="960aaa2962206a5fb57f742bf48c86b96895465112011d1959de3f193fd8f20a"
_nes_sum="bbd7ded4194b40d57ee740e2ac7ea8bb88b06f3c27cde919e392614d8fec3d1a"
_nes_sig_sum="ce420fe609ea298f43a1380db2d5e6c9fcf12a1ac0bae1af503c323da2832dab"
_pic_famicom_sum="6f2d2e69d282a3d31217b4bd955cd8e8e8b1c55a5bb8421e1d24f184e75149d7"
_pic_famicom_sig_sum="e61cbab0c7e3933aa219216f6c818e6f5ffeda21543d9e9d5b9226de8a460d54"
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
# ethereum
_network="1"
# gnosis
_network="100"
_pic_network="${_network}"
_sig_network="${_network}"
# File system addresses
_fs=(
  ["1946"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["3940"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["62831"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["555666"]="0x629d369Edd5f64391f0bA6187F2794D7b54F7e57"
  ["37111"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["10143"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["80002"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["10200"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
  ["11155111"]="0x151920938488F193735e83e052368cD41F9d9362"
  ["97"]="0x7D55E8B250DC2393255d62db57C4C8bF7BCf23ec"
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
_pic_file_system="${_fs["${_pic_network}"]}"
_sig_file_system="${_fs["${_sig_network}"]}"
_evmfs_dir="evmfs://${_sig_network}/${_file_system}/${_ns}"
_evmfs_sig_dir="evmfs://${_network}/${_sig_file_system}/${_sig_ns}"
_evmfs_pic_dir="evmfs://${_network}/${_pic_file_system}/${_ns}"
_famicom_uri="${_evmfs_dir}/${_famicom_sum}"
_famicom_sig_uri="${_evmfs_sig_dir}/${_famicom_sig_sum}"
_nes_uri="${_evmfs_dir}/${_nes_sum}"
_nes_sig_uri="${_evmfs_sig_dir}/${_nes_sig_sum}"
_pic_famicom_uri="${_evmfs_pic_dir}/${_pic_famicom_sum}"
_pic_famicom_sig_uri="${_evmfs_sig_dir}/${_pic_famicom_sig_sum}"
source=(
)
sha256sums=(
)
if [[ "${_evmfs}" == "true" ]]; then
  makedepends+=(
    "evmfs"
    "${_xz_archiver}"
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
  _famicom_src="${_app_id}.FamiCom.fds.tar.xz::${_famicom_uri}"
  _nes_src="${_app_id}.NES.nes.tar.xz::${_nes_uri}"
  _pic_famicom_src="${_app_id}.FamiCom.png::${_pic_famicom_uri}"
  _famicom_sig_src="${_app_id}.FamiCom.fds.tar.xz.sig::${_famicom_sig_uri}"
  _nes_sig_src="${_app_id}.NES.nes.tar.xz.sig::${_nes_sig_uri}"
  _pic_famicom_sig_src="${_app_id}.FamiCom.png.sig::${_pic_famicom_sig_uri}"
  source+=(
    "${_pic_famicom_sig_src}"
  )
  sha256sums+=(
    "${_pic_famicom_sig_sum}"
  )
  if [[ "${_famicom}" == "true" ]]; then
    source+=(
      "${_famicom_sig_src}"
    )
    sha256sums+=(
      "${_famicom_sig_sum}"
    )
  fi
  if [[ "${_nes}" == "true" ]]; then
    source+=(
      "${_nes_sig_src}"
    )
    sha256sums+=(
      "${_nes_sig_sum}"
    )
  fi
fi
if [[ "${_dl_agent}" == "true" ]]; then
  source+=(
    "${_pic_famicom_src}"
  )
  sha256sums+=(
    "${_pic_famicom_sum}"
  )
  if [[ "${_famicom}" == "true" ]]; then
    source+=(
      "${_famicom_src}"
    )
    sha256sums+=(
      "${_famicom_sum}"
    )
  fi
  if [[ "${_nes}" == "true" ]]; then
    source+=(
      "${_nes_src}"
    )
    sha256sums+=(
      "${_nes_sum}"
    )
  fi
fi

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
  if [[ "${_famicom}" == "true" ]]; then
    lrunzip \
      -z \
      --outfile "${_app_id}.FamiCom.fds" -- \
      "${_app_id}.FamiCom.fds.tar.xz" || \
    true
  fi
  if [[ "${_nes}" == "true" ]]; then
    lrunzip \
      -z \
      --outfile "${_app_id}.NES.nes" -- \
      "${_app_id}.NES.nes.tar.xz" || \
    true
  fi
}

prepare() {
  local \
    _sum \
    _download \
    _extract \
    _famicom_launcher_create_opts=() \
    _nes_launcher_create_opts=()
  _download="false"
  _extract="false"
  if [[ "${_dl_agent}" == "false" ]]; then
    _evmfs_get \
      "${_app_id}.FamiCom.png" \
      "${_pic_famicom_sum}" \
      "${_pic_famicom_uri}"
  fi
  if [[ "${_famicom}" == "true" ]]; then
    _famicom_launcher_create_opts=(
      -v
      -t
        "${_game_title}"
      -d
        "${pkgdesc}"
      -p
        "famicom"
      -e
        "${_emulator}"
      -U
        "${_uuid_ja}"
      -o
        "${srcdir}/${_pkg}-famicom"
    )
    videogame-launcher-create \
      "${_famicom_launcher_create_opts[@]}" \
      "${_app_id}.FamiCom"
    if [[ -e "${_app_id}.fds" ]]; then
      mv \
        "${_app_id}.fds" \
        "${_app_id}.FamiCom.fds"
    fi
    _download="false"
    _extract="false"
    if [[ "${_dl_agent}" == "false" ]]; then
      _evmfs_get \
        "${_app_id}.FamiCom.fds.tar.xz" \
        "${_famicom_sum}" \
        "${_famicom_uri}"
    fi
    if [[ ! -e "${_app_id}.fds" && \
          ! -e "${_app_id}.FamiCom.fds" ]]; then
      _extract="true"
    fi
  fi
  if [[ "${_nes}" == "true" ]]; then
    if [[ -e "${_app_id}.fds" ]]; then
      mv \
        "${_app_id}.nes" \
        "${_app_id}.NES.nes"
    fi
    cp \
      "${_app_id}.FamiCom.png" \
      "${_app_id}.NES.png"
    _nes_launcher_create_opts=(
      -v
      -t
        "${_game_title} (NES)"
      -d
        "${pkgdesc}. Nintendo Entertainment System port."
      -p
        "nes"
      -e
        "${_emulator}"
      -U
        "${_uuid_en}"
      -o
        "${srcdir}/${_pkg}-nes"
    )
    videogame-launcher-create \
      "${_nes_launcher_create_opts[@]}" \
      "${_app_id}.NES"
    if [[ -e "${_app_id}.nes" ]]; then
      mv \
        "${_app_id}.nes" \
        "${_app_id}.NES.nes"
    fi
    _download="false"
    _extract="false"
    if [[ "${_dl_agent}" == "false" ]]; then
      _evmfs_get \
        "${_app_id}.NES.nes.tar.xz" \
        "${_famicom_sum}" \
        "${_famicom_uri}"
    fi
    if [[ ! -e "${_app_id}.nes" && \
          ! -e "${_app_id}.NES.nes" ]]; then
      _extract="true"
    fi
    if [[ "${_extract}" == "true" ]]; then
      _rom_extract
    fi
  fi
}

_icon_install() {
  local \
    _app_id="${1}" \
    _uuid="${2}"
  install \
    -vDm755 \
    "${_app_id}.png" \
    "${pkgdir}/usr/share/icons/${_app_id}-${_uuid}.png"
}

_desktop_file_install() {
  local \
    _app_id="${1}"
  install \
    -vDm755 \
    "${_app_id}.desktop" \
    "${pkgdir}/usr/share/applications/${_app_id}.desktop"
}

_launcher_install() {
  local \
    _app_id="${1}" \
    _uuid="${2}" \
    _icon_name
  _icon_name="${_app_id}"
  if (( 2 < "$#" )); then
    _icon_name="${3}"
  fi
  _icon_install \
    "${_app_id}" \
    "${_uuid}"
  _desktop_file_install \
    "${_app_id}"
}

_lang_provides() {
  local \
    _pkg="${1}" \
    _pkgver="${2}" \
    _langs=()
  shift \
    2
  _langs+=(
    "$@"
  )
  for _lang in "${_langs[@]}"; do
    provides+=(
      "${_pkg}-${_lang}=${pkgver}"
    )
  done
}

package_super-mario-bros-2-famicom() {
  local \
    _games_dir \
    _game_dir \
    _lang \
    _usr \
    _install_shared_opts=() \
    _termux_shortcut_new_opts=() \
    _data_path
  pkgdesc="${pkgdesc}. FamiCom Japanese version."
  _usr="$( \
    _usr_get)"
  _games_dir="${_usr}/games"
  _game_dir="${_games_dir}/${_app_id}"
  provides=(
    "${_pkg}=${pkgver}"
    "${_pkg}-the-lost-levels=${pkgver}"
    "${_pkg}-ja=${pkgver}"
  )
  _lang_provides \
    "${_pkg}" \
    "${pkgver}" \
    "ja"
  _lang_provides \
    "${_pkg}-famicom" \
    "${pkgver}" \
    "ja"
  install \
    -vDm755 \
    "${_pkg}-famicom" \
    "${pkgdir}/usr/bin/${_pkg}-famicom"
  ln \
    -s \
    "${_usr}/bin/${pkgbase}-famicom" \
    "${pkgdir}/usr/bin/${_pkg}"
  _launcher_install \
    "${_app_id}.FamiCom" \
    "${_uuid_ja}"
  install \
    -vdm755 \
    "${pkgdir}/usr/games/${_app_id}.FamiCom"
  if [[ "${_os}" == "Android" ]]; then
    _data_path="/storage/emulated/0/Android/media/${_app_id}"
    _install_shared_opts+=(
      -v
      "${srcdir}/${_app_id}.FamiCom.fds"
      "${pkgdir}"
      "/usr/games/${_app_id}"
      "Android/media/${_app_id}"
      "${_uuid_ja}.fds"
    )
    termux-install-shared \
      "${_install_shared_opts[@]}"
    install \
      -vdm755 \
      "${pkgdir}/home/.shortcuts"
    _termux_shortcut_new_opts+=(
      -v
      -o
        "${pkgdir}/home/.shortcuts"
    )
    termux-shortcut-new \
      "${_termux_shortcut_new_opts[@]}" \
      "${_app_id}.FamiCom.desktop"
    install \
      -vDm644 \
      "${srcdir}/${_app_id}.FamiCom.png" \
      "${pkgdir}/home/.shortcuts/icons/${_game_title} (${_uuid_ja}).png"
  elif [[ "${_os}" == "GNU/Linux" ]]; then
    _data_path="${_game_dir}"
    install \
      -vDm644 \
      "${srcdir}/${_app_id}.FamiCom.fds" \
      "${pkgdir}/usr/games/${_app_id}/${_uuid_ja}.fds"
  fi
  for _lang in "any" \
               "ja"; do
    echo \
      "${_data_path}/${_uuid_ja}.fds" > \
      "${pkgdir}/usr/games/${_app_id}.FamiCom/${_lang}"
  done
}

package_super-mario-bros-2-nes() {
  local \
    _games_dir \
    _game_dir \
    _lang \
    _usr \
    _install_shared_opts=() \
    _termux_shortcut_new_opts=() \
    _data_path \
    _pkgdesc=()
  _pkgdesc=(
    "${pkgdesc}."
    "Nintendo Entertainment System version."
  )
  pkgdesc="${_pkgdesc[*]}"
  _usr="$( \
    _usr_get)"
  _games_dir="${_usr}/games"
  _game_dir="${_games_dir}/${_app_id}"
  provides=(
    "${_pkg}=${pkgver}"
    "${_pkg}-the-lost-levels=${pkgver}"
    "${_pkg}-en=${pkgver}"
  )
  _lang_provides \
    "${_pkg}" \
    "${pkgver}" \
    "en"
  _lang_provides \
    "${_pkg}-nes" \
    "${pkgver}" \
    "en"
  install \
    -vDm755 \
    "${_pkg}-nes" \
    "${pkgdir}/usr/bin/${_pkg}-nes"
  _launcher_install \
    "${_app_id}.NES" \
    "${_uuid_en}"
  install \
    -vdm755 \
    "${pkgdir}/usr/games/${_app_id}.NES"
  if [[ "${_os}" == "Android" ]]; then
    _data_path="/storage/emulated/0/Android/media/${_app_id}"
    _install_shared_opts+=(
      -v
      "${srcdir}/${_app_id}.NES.nes"
      "${pkgdir}"
      "/usr/games/${_app_id}"
      "Android/media/${_app_id}"
      "${_uuid_en}.nes"
    )
    termux-install-shared \
      "${_install_shared_opts[@]}"
    install \
      -vdm755 \
      "${pkgdir}/home/.shortcuts"
    _termux_shortcut_new_opts+=(
      -v
      -o
        "${pkgdir}/home/.shortcuts"
    )
    termux-shortcut-new \
      "${_termux_shortcut_new_opts[@]}" \
      "${_app_id}.NES.desktop"
    install \
      -vDm644 \
      "${srcdir}/${_app_id}.NES.png" \
      "${pkgdir}/home/.shortcuts/icons/${_game_title} (NES) (${_uuid_en}).png"
  elif [[ "${_os}" == "GNU/Linux" ]]; then
    _data_path="${_game_dir}"
    install \
      -vDm644 \
      "${srcdir}/${_app_id}.NES.nes" \
      "${pkgdir}/usr/games/${_app_id}/${_uuid_en}.nes"
  fi
  for _lang in "any" \
               "en"; do
    echo \
      "${_data_path}/${_uuid_en}.nes" > \
      "${pkgdir}/usr/games/${_app_id}.NES/${_lang}"
  done
}

# vim:set sw=2 sts=-1 et:
