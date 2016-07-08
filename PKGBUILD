# Maintainer: Ralf Morawe <mowalle.dev@gmail.com>
pkgname=libmesasr-bin
pkgver=1.0.14_748
pkgrel=1
pkgdesc="Linux user-side driver for Mesa-Imaging Swiss Ranger Cameras"
arch=('x86_64')
url='http://hptg.com/industrial/'
license=('unknown')
depends=('libusb' 'glibc')
source=('http://downloads.mesa-imaging.ch/dlm.php?fname=./customer/driver/libmesasr-dev-1.0.14-748.amd64.deb')
md5sums=('30d2c3bd93402888e8f47b80a1008ed8')

package() {
    tar -zxf data.tar.gz -C "${pkgdir}"

    # Prepare permissions of to-be-copied directories and files.
    # Prevents warnings about permission mismatch between file system and folders.
    find ${pkgdir} -type d ! -perm 755 -exec chmod 755 {} +
    find ${pkgdir} -type f ! -perm 644 -exec chmod 644 {} +

    # Change libMesaSRTester persmissions, so that it is executable again
    chmod 755 "${pkgdir}/usr/bin/libMesaSRTester"
}
