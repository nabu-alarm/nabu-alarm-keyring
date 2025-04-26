pkgname=nabu-alarm-keyring
pkgver=1
pkgrel=2
pkgdesc="GPG keyring for nabu-alarm repo"
arch=('any')
url="https://youruser.github.io/arch-repo"
license=('MIT')
source=("nabu-key")
b2sums=('87eb1b3b323b767734a256ed50167c6d19d3a292092ce9eb490a582f7649ad3e7b048bc07014ac42e7175b206d567b8161d1e11560c98512dbb91ff775893a7f')
package() {
  install -Dm644 "$srcdir/nabu-key" "$pkgdir/usr/share/pacman/keyrings/nabu-alarm.gpg"
  printf "%s:4:" "$(gpg --with-colons --show-keys nabu-key | awk -F: '/^fpr:/ { print $10; exit }')" >nabu-alarm-trusted
  install -Dm644 nabu-alarm-trusted "$pkgdir/usr/share/pacman/keyrings/nabu-alarm-trusted"
  rm nabu-alarm-trusted
}
