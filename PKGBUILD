pkgname=dotdeploy
pkgver=1.0.0
pkgrel=0
pkgdesc=".deploy daemon and ctl"
arch=("any")
url="https://github.com/gohryt/dotdeploy"
license=("GPL3")

makedepends=("go>=1.22")
options=(!debug)

source=("$url/archive/main/$pkgname.tar.gz")
sha256sums=("SKIP")

provides=("$pkgname=$pkgver")

build() {
	export GOFLAGS='-buildmode=pie -trimpath'

	cd "$pkgname-main"

	go build -trimpath -o deployd   ./cmd/deployd
	go build -trimpath -o deployctl ./cmd/deployctl
}

package() {
	cd "$pkgname-main"

	install -Dm755 deployd   -t "$pkgdir"/usr/bin
	install -Dm755 deployctl -t "$pkgdir"/usr/bin
}
