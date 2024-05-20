pkgname=dotdeploy
pkgver=0.2.1
pkgrel=0
pkgdesc=".deploy ctl and daemon"
arch=("any")
url="https://github.com/gohryt/dotdeploy"
license=("GPL3")

makedepends=("go>=1.22")
options=(!debug)

source=("$url/archive/v$pkgver/$pkgname-$pkgver.tar.gz")
sha256sums=("05a0495e9a3a2ba2de98948fb47a789f2cdd05f871cfd278fc6f8a499f7967d9")

provides=("$pkgname=$pkgver")

build() {
	cd "$pkgname-$pkgver"

	go build -trimpath -o deployd   ./cmd/deployd
	go build -trimpath -o deployctl ./cmd/deployctl
}

package() {
	cd "$pkgname-$pkgver"

	install -Dm755 deployd   -t "$pkgdir"/usr/bin
	install -Dm755 deployctl -t "$pkgdir"/usr/bin
}
