# Maintainer: rodriguezst <git@rodriguezst.es>

pkgname=nabu-tweaks
pkgver=20$(date +%y%m%d)
pkgrel=1
pkgdesc="Tweaks needed to run Manjaro ARM on Xiaomi Pad 5"
arch=('any')
url="https://www.manjaro.org"
license=('GPL')
depends=('gzip' 'glibc-locales' 'alsa-ucm-conf')
source=("nabu-post-install"
        "nabu-post-install.service"
        "HiFi.conf"
        "sm8150.conf"
        "fstab"
        "kwinoutputconfig.json")
install=$pkgname.install
sha256sums=('709dd529c2db86798d932c32290f0325f176f133eb3352ebff774d046d7f3359'
            '0aeabb442cd26c3d2233b19b4364471181b0c7b0dfeba8808361dc4435e27011'
            'ed77796bc8178cb75caf2fe9e8fc9e05f96e20a2e6ad00f47a8e7d893ad9c769'
            '4393bc0f80d81c96913a1eb27e1a463ced16c7c6a36d116b9db1fda88f0b7ca3'
            'a507c861b0884d9b434d0fdf9ab7c24da8dbdc7c5a2872528d48e264ded7d433'
            'f782f8690b0b2afae07701c10d40e1a5dabfdcc5ad871188541df1cbf34ae9cc')

package() {
    depends=('qbootctl' 'rmtfs' 'pd-mapper' 'tqftpserv')
    install -Dm755 "${srcdir}/nabu-post-install" -t "${pkgdir}/usr/bin/"
    install -Dm644 "${srcdir}/nabu-post-install.service" -t "${pkgdir}/usr/lib/systemd/system/"
    # Install ALSA UCM profiles
    install -Dm644 "${srcdir}/HiFi.conf" -t "${pkgdir}/usr/share/alsa/ucm2/Xiaomi/nabu/"
    install -Dm644 "${srcdir}/sm8150.conf" -t "${pkgdir}/usr/share/alsa/ucm2/conf.d/sm8150/"
    # Install fstab
    install -Dm644 "${srcdir}/fstab" -t "${pkgdir}/etc/fstab"
    # Copy other files for post_install routine
    install -Dm644 "${srcdir}/kwinoutputconfig.json" -t "${pkgdir}/opt/nabu-tweaks/kwin/kwinoutputconfig.json"
}
