# Maintainer: tanuva <tanuva aet nightsoul d00t org>

pkgname='gtk-theme-gnome-cupertino-glassy'
pkgver=2.0pre1
pkgrel=2
pkgdesc="Gnome Cupertino GTK3 theme with Snow-Leopard-like (larger) metacity icons"
arch=(any)
url="http://gnome-look.org/content/show.php?content=147061"
license=('GPL')
depends=('gtk-engine-unico' 'gtk-engine-murrine')
conflicts=('gtk-theme-gnome-cupertino' 'gtk-theme-adwaita-cupertino')
replaces=('gtk-theme-adwaita-cupertino-glassy')
source=('http://gnome-look.org/CONTENT/content-files/147061-Gnome-Cupertino.tar.gz')
install=gtk-theme-gnome-cupertino.install

package() {
 	bsdtar -xf ${srcdir}/147061-Gnome-Cupertino.tar.gz

	# replace Lion metacity icons with Snow Leopard ones
	tar -C ${srcdir}/Gnome-Cupertino/metacity-1/ -xf ${srcdir}/Gnome-Cupertino/metacity-sl-buttons.tar.gz
	tar -C ${srcdir}/Gnome-Cupertino-unity/metacity-1/ -xf ${srcdir}/Gnome-Cupertino-unity/unity-sl-buttons.tar.gz

	mkdir -p ${pkgdir}/usr/share/themes
	cp -R ${srcdir}/Gnome-Cupertino*  ${pkgdir}/usr/share/themes/
	cd ${pkgdir}/usr/share/themes/
	find . -type f -exec chmod 644 {} \;
	find . -type d -exec chmod 755 {} \;
}

md5sums=('c16e3cd975da22fed2e6db56e22ffe7e')
