pkgname=xenonlinux-bspwm
pkgrel=1
pkgdesc="bspwm config for xenonlinux"
arch=('any')
url="https://github.com/Xenon-Linux/xenonlinux-bspwm"
license=('GPL3')
depends=('bspwm' 'sxhkd' 'feh' 'alsa-utils' 'rofi' 'polybar' 'dunst' 'i3lock')
optdepends=('alacritty: terminal'
            'pcmanfm-gtk3: file manager'
            'picom: compositor'
            'firefox: browser'
            'mpd: music daemon'
            'ncmpcpp: music player'
            'mpv: media player'
            'network-manager-applet: menu for nm'
            'scrot: screenshot tool'
)
install="${pkgname}.install"

prepare(){
  	cp -af ../config/. "$srcdir"
}

package(){
  local skeldir="$pkgdir"/etc/skel/.config
	local configdir="$skeldir"/.config
	local wmdir="$configdir"/bspwm

	mkdir -p "$skeldir" && mkdir -p "$configdir" && mkdir -p "$wmdir"
  cp -r ${srcdir}/* "$configdir"
  chmod -R +x "${wmdir}"
  install -Dm 755 ${srcdir}/bspwm/bspwmrc "${wmdir}"/bspwmrc
}
