# Maintainer: callmetango
# Contributor: Antonio Rojas <arojas@archlinux.org>

pkgname=sonic-audio-applet-pulse
pkgver=6.6.5
pkgrel=1
pkgdesc='SonicDE applet for audio volume management using PulseAudio'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-audio-applet-pulse'
license=(LGPL-2.0-or-later)
depends=(gcc-libs
         glib2
         glibc
         kcmutils
         kconfig
         kdbusaddons
         kdeclarative
         ki18n
         kirigami-addons
         kitemmodels
         kstatusnotifieritem
         ksvg
         libcanberra
         libpulse
         pulse-native-provider
         pulseaudio-qt
         qt6-base
         qt6-declarative
         sonic-frameworks-core-addons
         sonic-frameworks-keybind
         sonic-frameworks-quick-ui
         sonic-interface-libraries
         sonic-workspace)
makedepends=(sonic-frameworks-cmake-modules
             sonic-frameworks-doctools)
provides=(plasma-pa)
conflicts=(plasma-pa)
groups=(sonicde)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('a29916efcb7b985b641bd0e75fcfa49960aa7433884d4689c5b802abf7e7575d')

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
