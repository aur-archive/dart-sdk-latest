# Maintainer: Usagi Ito <usagi@WonderRabbitProject.net>
pkgname=dart-sdk-latest
pkgver=20120317
pkgrel=1
pkgdesc="the Dart language SDK. (latest continuous version; it's DANGEROUSLY)"
arch=('i686' 'x86_64')
url="http://www.dartlang.org/docs/getting-started/sdk/"
license=('BSD')
depends=('unzip' 'wget')
optdepends=()
makedepends=()
provides=()
conflicts=(dart-sdk)
replaces=()
source=()
install=
changelog=
noextract=()
md5sums=()

zip_url='http://gsdview.appspot.com/dart-editor-archive-continuous/latest/dart-linux.zip'
zip_filename=`basename ${zip_url}`
ziped_directory='dart-sdk'

build(){
  pushd $srcdir
  
  msg 'get the binary'
  if [ -f $zip_filename ]
  then
    rm -rf $zip_filename
  fi
  wget -N $zip_url
  if [ -d $ziped_directory ]
  then
    rm -rf $ziped_directory
  fi
  unzip $zip_filename
  chmod -R +r $ziped_directory/
  chmod -R +x $ziped_directory/bin/*

  popd
}

package(){
  destination_directory=${pkgdir}/usr/local
  mkdir -p $destination_directory
  cp -a ${srcdir}/$ziped_directory/* $destination_directory
  find $destination_directory -type d -print | xargs chmod +x
}

