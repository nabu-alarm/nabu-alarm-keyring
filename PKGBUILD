pkgname=nabu-alarm-keyring
pkgver=1
pkgrel=1
pkgdesc="GPG keyring for nabu-alarm repo"
arch=('any')
url="https://youruser.github.io/arch-repo"
license=('MIT')
source=("nabu-key")
b2sums=('90c1d54d2b6aff6649b7064df605db9d76b0cbbfcfddddc05ea94cc20d2ee19c57b7727294f61311ba80b5e906aa911f23d169d0b139092e1cfcfbbe62bae834')
package() {
  install -Dm644 "$srcdir/nabu-key" "$pkgdir/usr/share/pacman/keyrings/nabu-alarm.gpg"
  gpg --with-colons --show-keys nabu-key | awk -F: '/^fpr:/ { print $10; exit }' >nabu-alarm-trusted
  install -Dm644 nabu-alarm-trusted "$pkgdir/usr/share/pacman/keyrings/nabu-alarm-trusted"
  rm nabu-alarm-trusted
}
