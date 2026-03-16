pkgname=mutt-wizard-oauth-git
pkgver=3.3.1.r163.g00b86f6
pkgrel=1
pkgdesc="mutt-wizard with OAuth2 support and systemd mailsync timer"
arch=('any')
url="https://github.com/cmlsharp/mutt-wizard"
license=('GPL3')
depends=('neomutt' 'isync' 'msmtp' 'gettext' 'ca-certificates')
optdepends=(
    'pass: password-based account authentication'
    'cyrus-sasl-xoauth2-git: OAuth2 support for mbsync (offline mode)'
    'goimapnotify: push notifications'
    'lynx: view HTML email'
    'notmuch: index and search mail'
    'abook: terminal address book'
    'urlview: extract URLs from email'
    'mpop: POP protocol support'
    'pam-gnupg: automatic GPG key unlock on login'
)
provides=('mutt-wizard')
conflicts=('mutt-wizard')
_commit=00b86f64b354fca1d973ac2c99b4ed3050b7ac9e
source=("$pkgname-$_commit.tar.gz::https://github.com/cmlsharp/mutt-wizard/archive/$_commit.tar.gz")
sha256sums=('0c15c83a89b905a5c706feb6114d97fe5d676169ee2aa7ff719847798f8d7f31')

pkgver() {
    cd "mutt-wizard-$_commit"
    git describe --long --tags 2>/dev/null | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g' || echo "$pkgver"
}

package() {
    cd "mutt-wizard-$_commit"
    make DESTDIR="$pkgdir" PREFIX=/usr install
}
