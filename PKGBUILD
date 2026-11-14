# Maintainer: Archlatam <corelinuxx@mail>

pkgname=core-plasma-settings
pkgver=1.0
pkgrel=2
pkgdesc="Configuración base de KDE de Arch Latam (instalada en /etc/skel)"
arch=('any')
url="https://github.com/archlatam/core-plasma-settings"
license=('GPL-3.0-only')
depends=('imagemagick')
optdepends=(
  'dolphin: configuración de dolphinrc'
  'konsole: perfiles y esquema de colores de Konsole'
  'fastfetch: config.jsonc para fastfetch'
)

source=()
sha256sums=()

options=('!strip')

package() {
  cd "$startdir"

  install -d "$pkgdir/etc"
  cp -a --no-preserve=ownership src/etc/skel "$pkgdir/etc/"

  find "$pkgdir/etc/skel" -type d -exec chmod 755 {} +
  find "$pkgdir/etc/skel" -type f -exec chmod 644 {} +

  install -Dm644 src/etc/xdg/kicker-extra-favoritesrc \
    "$pkgdir/etc/xdg/kicker-extra-favoritesrc"

  install -Dm644 LICENSE \
    "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
