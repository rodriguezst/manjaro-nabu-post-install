# Maintainer: rodriguezst <git@rodriguezst.es>

pkgname=nabu-post-install
pkgver=20$(date +%y%m%d)
pkgrel=1
pkgdesc="Manjaro ARM's Xiaomi Pad 5 post install script"
arch=('any')
url="https://www.manjaro.org"
license=('GPL')
depends=('gzip' 'glibc-locales' 'qbootctl' 'rmtfs' 'pd-mapper' 'tqftpserv' 'alsa-ucm-conf')
source=("nabu-post-install"
        "nabu-post-install.service"
        "HiFi.conf"
        "sm8150.conf")
install=$pkgname.install
sha256sums=('98d3bbf47675a0b1393ca2f3ddb0377ff9a150b47648a30ce6e25c3775b6c90c'
            '0aeabb442cd26c3d2233b19b4364471181b0c7b0dfeba8808361dc4435e27011'
            'ed77796bc8178cb75caf2fe9e8fc9e05f96e20a2e6ad00f47a8e7d893ad9c769'
            '4393bc0f80d81c96913a1eb27e1a463ced16c7c6a36d116b9db1fda88f0b7ca3')

package() {
    install -Dm755 "${srcdir}/nabu-post-install" -t "${pkgdir}/usr/bin/"
    install -Dm644 "${srcdir}/nabu-post-install.service" -t "${pkgdir}/usr/lib/systemd/system/"
    # Install ALSA UCM profiles
    install -Dm644 "${srcdir}/HiFi.conf" -t "${pkgdir}/usr/share/alsa/ucm2/Xiaomi/nabu/"
    install -Dm644 "${srcdir}/sm8150.conf" -t "${pkgdir}/usr/share/alsa/ucm2/conf.d/sm8150/"
}
