# Maintainer: Sergey Kostyuk <ks.hot.ua@gmail.com>

# Based on original 
pkgname=infinit
pkgver=0.9.39
pkgrel=1
pkgdesc="Send files and folders of any size or format."
arch=('x86_64')
url="https://infinit.io/"
license=('custom:infinit')
depends=('curl' 'qt4' 'qtwebkit' 'libgap' 'libqxt' 'libpng12' 'libarchive' 'fuse' 'zlib' 'openssl')
# Must be in depends but version-specific or not available either in AUR or official repos:
#depends+=('boost-libs=1.56.0' 'libaws')
options=(!strip)
source=("${pkgname}.desktop"
		"terms-and-conditions.html::https://infinit.io/legal"
		"${pkgname}.png::https://infinit.io/images/press/logos/logo.png")
source_x86_64=("https://infinit.io/downloads/${pkgname}_${pkgver}_amd64.deb")
md5sums=('4b285f98f30716e3abb3876ec7a43de9'
		 'SKIP'
		 '6ad5976c6f29f5202f44144206c0249b')
md5sums_x86_64=('9cf29795e5a6509df0c57b92085a069b')

package() {
	# Unpack nested archieve
	tar xzf data.tar.gz -C "${srcdir}/nested"

	# Extract binary
	install -Dm755 "${srcdir}/nested/opt/infinit/bin/Infinit" \
		"{$pkgdir}/usr/bin/Infinit"

	# Libaws
	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libaws.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libaws.so"	

	# Extract app-libs
	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libfrete.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libfrete.so"	

	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libprotocol.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libprotocol.so"	

	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libpapier.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libpapier.so"	

	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libmetrics.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libmetrics.so"	

	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libcryptography.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libcryptography.so"	

	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libreactor.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libreactor.so"	

	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libcrash.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libcrash.so"	



	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libaws.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libaws.so"

	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libaws.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libaws.so"

	install -Dm755 "${srcdir}/nested/opt/infinit/lib/libaws.so" \
		"{$pkgdir}/usr/lib/${pkgname}/libaws.so"

	# Copy additional files
	install -Dm644 "terms-and-conditions.html" \
		"${pkgdir}/usr/share/licenses/${pkgname}/terms-and-conditions.html"

	install -Dm644 "${pkgname}.desktop" \
    	"{$pkgdir}/usr/share/applications/${pkgname}.desktop"

    install -Dm644 "${pkgname}.png" \
    	"{$pkgdir}/usr/share/pixmaps/infinit.png"
}

