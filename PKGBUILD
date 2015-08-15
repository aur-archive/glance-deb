# Maintainer: James Bulmer <nekinie@gmail.com>

pkgname="glance-deb"
pkgver=2014.1
pkgrel=2
pkgdesc="Openstack image"
arch=("i686" "x86_64")
url="http://docs.openstack.org/developer/glance/"
license=("Apache")
groups=("openstack-deb")

depends=(
  "python2"
  "python2-pbr"
  "python2-greenlet"
  "python2-sqlalchemy"
  "python2-openstack-migrate"
  "python2-anyjson"
  "python2-eventlet"
  "python2-paste-deploy"
  "python2-paste"
  "python2-routes"
  "python2-webob"
  "python2-boto"
  "python2-httplib2"
  "python2-kombu"
  "python2-crypto"
  "python2-iso8601"
  "python2-ordereddict"
  "python2-oslo-config"
  "python2-stevedore"
  "python2-jsonschema"
  "python2-cinderclient"
  "python2-keystoneclient"
  "python2-glanceclient"
  "python2-pyopenssl"
  "python2-six"
  "python2-oslo-messaging"
  "python2-swiftclient"
  "python2-oslo-vmware"
)

makedepends=("python2-setuptools")

conflicts=(
  "glance",
  "openstack-glance-git"
 )

source=("http://archive.ubuntu.com/ubuntu/pool/main/g/glance/glance_${pkgver}.orig.tar.gz")
md5sums=("f6514c0b508c5cb93c5024e1676ea56a")

build() {
  cd "${srcdir}/glance-${pkgver}/"
  python2 setup.py build
}

package() {
  cd "${srcdir}/glance-${pkgver}/"
  python2 setup.py install --root="${pkgdir}/" --optimize=1
  mkdir "${pkgdir}/etc/"
  cp -a "etc" "${pkgdir}/etc/glance"
}