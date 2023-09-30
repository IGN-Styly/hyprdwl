# Maintainer: Styly <claudioresendeptbr@gmail.com>
pkgname=hyprdwl
pkgver=0.1
pkgrel=1
pkgdesc="Split monitor workspaces for Hyprland, so it can be just like dwm"
arch=('x86_64')
url="https://github.com/Duckonaut/split-monitor-workspaces"
license=('GPL')
depends=(cairo
         hyprland
         gcc-libs
         glibc
         glslang
         libdisplay-info
         libdrm
         libglvnd
         libinput
         libliftoff
         libx11
         libxcb
         libxcomposite
         libxfixes
         libxkbcommon
         libxrender
         opengl-driver
         pango
         pixman
         pixman
         polkit
         seatd
         systemd-libs
         vulkan-icd-loader
         vulkan-validation-layers
         wayland
         wayland-protocols
         xcb-proto
         xcb-util
         xcb-util-errors
         xcb-util-keysyms
         xcb-util-renderutil
         xcb-util-wm
         xorg-xinput
         xorg-xwayland)
depends+=(libdisplay-info.so)
makedepends=(cmake
             gdb
             meson
             ninja
             vulkan-headers
             xorgproto
             git
           )

source=(
  "git+https://github.com/Duckonaut/split-monitor-workspaces.git"
  "git+https://github.com/hyprwm/Hyprland.git"  
)
sha256sums=('SKIP'
            'SKIP')


prepare() {
    export HYPRLAND_HEADERS="$HOME/repos/Hyprland"
}

build() {
	cd "split-monitor-workspaces"
	make all
  echo "Add 'exec-once=hyprctl plugin load /usr/lib/split-monitor-workspaces.so' to your hyprland config."
}
package(){
  cd split-monitor-workspaces
  install -Dm0775 ./split-monitor-workspaces.so "$pkgdir/usr/lib/split-monitor-workspaces.so"
}
