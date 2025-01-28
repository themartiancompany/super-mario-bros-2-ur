# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>

_os="$( \
  uname \
    -o)"
_nes_emulator="fceux"
_dl_agent="true"
if [[ "${_os}" == "Android" ]]; then
  _zpaq_archiver="zpaq"
elif [[ "${_os}" == "GNU/Linux" ]]; then
  _zpaq_archiver="lrzip"
fi
_archive="false"
_evmfs="true"
_app_id="com.nintendo.SuperMarioBros"
_title="Super Mario Bros"
_rom_filename=""
_pkg=super-mario-bros
pkgname="${_pkg}"
pkgver=1.0
pkgrel=1
_pkgdesc=(
  "Platform game developed and published in 1985 by Nintendo"
  "for the Famicom in Japan and for the Nintendo Entertainment"
  "System (NES) in North America"
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'any'
)
url="https://en.wikipedia.org/wiki/${_title}"
depends=(
  "${_nes_emulator}"
)
makedepends=()
_archive="https://archive.org"
_wikimedia="https://upload.wikimedia.org"
license=(
  "custom"
)
_dmca_exemption="${_archive}/about/dmca.php"
_archive_namespace="download/nes-roms"
_archive_rom_url="${_archive}${_archive_namespace}/Super%20Mario%20Bros.%20%28World%29.nes"
_wikimedia_namespace="wikipedia/en"
_network=100 # gnosis
_file_system="0x69470b18f8b8b5f92b48f6199dcb147b4be96571" # default file system deployment
_namespace="0x926acb6aA4790ff678848A9F1C59E578B148C786" # that kid address
_rom_hash="684feefca60a36aa4d1a455ab8db17d8ecf1bb840fc92505f7ed6e6d5357c46b"
_pic_hash="2b7b72fe313c3c544c58d718b9f8f9abea957091c0070ba233234c7e4d0f0a95"
_evmfs_rom_uri="evmfs://${_network}/${_file_system}/${_namespace}/${_rom_hash}"
_evmfs_pic_uri="evmfs://${_network}/${_file_system}/${_namespace}/${_pic_hash}"
source=(
  "nes-template.desktop"
)
sha256sums=(
  "e021676ce1a72920536fad3733b4d5beb703f27da88f3418a517c675f0572a24"
)
if [[ "${_archive}" == "true" ]]; then
  _rom="${_app_id}.nes::${_archive_rom_uri}"
  _rom_sum="0b3d9e1f01ed1668205bab34d6c82b0e281456e137352e4f36a9b2cfa3b66dea"
  # This one could change actually because Wikipedia users can update
  # this and they have to delete the previous version.
  # So you know, another reason to use the evmfs as default.
  _pic_uri="${_wikimedia}/${_namespace}/0/03/Super_Mario_Bros._box.png"
elif [[ "${_evmfs}" == "true" ]]; then
  makedepends+=(
    "evmfs"
    "${_zpaq_archiver}"
  )
  if [[ ! " ${DLAGENTS[*]} " == " evmfs::" ]]; then
    _msg=(
      "no download agent configured to manage"
      "Ethereum Virtual Machine File System"
      "resources (evmfs://<uri>). The download"
      "will happen in the 'prepare' function"
    )
    msg \
      "${_msg[*]}"
    _dl_agent="false"
  fi
  _rom="${_app_id}.nes.zpaq::${_evmfs_rom_uri}"
  _rom_sum="${_rom_hash}"
  _pic_uri="${_evmfs_pic_uri}"
fi
if [[ "${_dl_agent}" == "true" ]]; then
  source+=(
    "${_rom}"
    "${_app_id}.png::${_pic_uri}"
  )
  sha256sums+=(
    "${_rom_sum}"
    "${_pic_hash}"
  )
fi

prepare() {
  local \
    _sum \
    _download
  _download="false"
  if [[ "${_dl_agent}" == "false" ]]; then
    if [[ ! -e "${_app_id}.nes.zpaq" ]]; then
      _download="true"
    else
      _sum="$( \
        sha256sum \
          "${_app_id}.nes.zpaq" | \
          awk \
            '{print $1}')"
      msg "${_sum}"
      if [[ "${_sum}" != "${_rom_sum}" ]]; then
        _download="true"
      fi
    fi
  fi
  if [[ "${_download}" == "true" ]]; then
    evmfs \
      -v \
      -o \
        "${srcdir}/${_app_id}.nes.zpaq" \
      get \
        "${_evmfs_rom_uri}"
    evmfs \
      -v \
      -o \
        "${srcdir}/${_app_id}.png" \
      get \
        "${_pic_uri}"
  fi
  if [[ ! -e "${_app_id}.nes" ]]; then
    lrunzip \
      -z \
      --outfile "${_app_id}.nes" -- \
      "${_app_id}.nes.zpaq"
  fi
  mv \
    nes-template.desktop \
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
    -i \
    "s/%_uuid%/${_uuid}/g" \
    "${_app_id}.desktop"
}

package() {
  install \
    -Dm755 \
    "${_app_id}.desktop" \
    "${pkgdir}/usr/share/applications/${_app_id}.desktop"
  install \
    -Dm644 \
    "${_app_id}.png" \
    "${pkgdir}/usr/share/icons/${_app_id}.png"
  install \
    -Dm644 \
    "${_app_id}.nes" \
    "${pkgdir}/usr/games/${_app_id}/${_app_id}.nes"
}

# vim:set sw=2 sts=-1 et:
