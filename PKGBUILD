# Maintainer: you but baset on tsn <tsn@rimit.ru>;
pkgname=1c_enterprise85
_pkgname1c=1C_Enterprise85
if test "$CARCH" == x86_64; then
    _pkgarch1c=$CARCH		# Если собираем пакеты для 64 бит
else
    _pkgarch1c=('i386')		# Если собираем пакеты для 32 бит
fi
pkgver=8.5.4         # Поменяйте на вашу версию
pkgrel=1878          # Поменяйте на вашу версию
_pkgname1c=1c-enterprise-$pkgver.$pkgrel
pkgdesc="1C 8.3 for Linux"
license=('custom')
arch=($CARCH)
options=('!strip')
#depends=('libwebkit' 'webkitgtk2') # Если не работает обновить liwebkit
depends=('freetype2' 'gtk3' 'libgsf' 'glib2' 'unixodbc' 'krb5' 'enchant' 'harfbuzz-icu' 'gst-plugins-base'
    'gst-plugins-good' 'gst-plugins-bad' 'libsecret' 'libsoup' 'sqlite' 'libxrender' 'libxfixes' 'libxslt'
    'geoclue' 'appmenu-gtk-module' 'gcc-libs' 'glib-networking' 'nuspell' 'hspell' 'libvoikko' 'aspell'
    'aspell-en' 'aspell-ru' 'webkit2gtk')
#makedepends=('pkgextract')
url="www.1c.ru"
source=(
$_pkgname1c-client-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-client-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-common-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-common-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-server-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-server-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-thin-client-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-thin-client-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-ws-$pkgver-$pkgrel.$_pkgarch1c.rpm
$_pkgname1c-ws-nls-$pkgver-$pkgrel.$_pkgarch1c.rpm
)

md5sums=('9418be0dbc81db32d89c8d5ac55a303c'
         '74874043b2d45d4578897657e7ff248c'
         '58ada2d554f33cc2ee4d381aa0e9d343'
         'e5442892201a1bee73c0297c3a9d4997'
         '1b3eb37ac14780aadf9c350d2f51fd4a'
         '9c0ba22a93a0057a4cd4c0559f51a21e'
         '58ae72d10beeb9861865a57c0797fdfd'
         '5f3f61e3c56b7b15412777348af0ae8f'
         '6d035a7a506c9d938f531a7b3916a9f9'
         '71fa2d6557b9a4556b6b1c2bdcffab20')
package() {

   cd $pkgdir

   rm -f $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libstdc++.so.6
   ln -s /usr/lib/libstdc++.so.6 $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libstdc++.so.6
   rm -f $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libgcc_s.so.1
   ln -s /usr/lib/libgcc_s.so.1 $srcdir/opt/1cv8/$arch/$pkgver.$pkgrel/libgcc_s.so.1

   cp -r $srcdir/usr $pkgdir
   cp -r $srcdir/opt $pkgdir
}
