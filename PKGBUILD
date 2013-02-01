# Maintainer: Neng Xu <neng2.xu2@gmail.com>

pkgname=orientdb-graphed
pkgver=1.3.0
pkgrel=1
pkgdesc="OrientDB Graph Edition, Document-Graph NoSQL with support of ACID Transactions, SQL and Native Queries, Asynchronous Commands, Intents, TinkerPop Blueprints / Gremlin, and much more"
arch=('any')
license=('Apache')
url="http://orientdb.org"
depends=('jre7-openjdk-headless')
install='orientdb.install'

source=(https://s3.amazonaws.com/orientdb/releases/${pkgname}-${pkgver}.tar.gz orientdb.sh orientdb.conf)
md5sums=('6326e99f45fce2359062144a923b750a'
  '1984b1d7b2e55e52b0f2840aefa5dcdb'
  'b1674253e357721eecf0bfe3107caa54')

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  install -m755 -d $pkgdir/opt/orientdb
  install -m700 -d $pkgdir/opt/orientdb/config
  install -m700 -d $pkgdir/opt/orientdb/databases
  install -m755 -d $pkgdir/opt/orientdb/bin
  install -m700 -d $pkgdir/opt/orientdb/www
  install -m755 -d $pkgdir/opt/orientdb/lib
  install -d $pkgdir/etc/rc.d
  install -d $pkgdir/etc/conf.d
  install -d $pkgdir/usr/bin

  # we don't install bechmarks and demo database

  install -m700 config/* $pkgdir/opt/orientdb/config/
  install -m700 bin/shutdown.sh bin/server.sh $pkgdir/opt/orientdb/bin/
  install -m755 bin/console.sh $pkgdir/opt/orientdb/bin/
  install -m755 lib/* $pkgdir/opt/orientdb/lib/
  cp -r www/* $pkgdir/opt/orientdb/www/

  # init scripts
  install -m755 ../orientdb.sh $pkgdir/etc/rc.d/orientdb
  install -m755 ../orientdb.conf $pkgdir/etc/conf.d/orientdb
}
