pkgname=mutt-wizard-oauth-git
pkgver=3.3.1.r165.g069155f
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
_commit=069155f4b4853cb3672e336dadcfc3b01b85dc09
source=("$pkgname-$_commit.tar.gz::https://github.com/cmlsharp/mutt-wizard/archive/$_commit.tar.gz")
sha256sums=('45b5e63218db69d50acb18688ffaddc8b41cb54665912499d31bb8a01d4b7377')

pkgver() {
    cd "mutt-wizard-$_commit"
    git describe --long --tags 2>/dev/null | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g' || echo "$pkgver"
}

package() {
    cd "mutt-wizard-$_commit"
    make DESTDIR="$pkgdir" PREFIX=/usr install
}
