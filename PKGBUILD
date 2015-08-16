# Contributor: Eric Forgeot < http://anamnese.online.fr >

pkgname=mines-of-elderlore
pkgver=1.0beta4
pkgrel=3
arch=('i686' 'x86_64')
pkgdesc="Out-of-challenge 7DRL roguelike developped further to balance easy gameplay and include graphics."
#url="http://landsof.elderlore.com/?q=fr/node/81"
url="http://roguebasin.roguelikedevelopment.org/index.php?title=Mines_of_Elderlore"
license=('GPL')
depends=('python-pygame' 'python-numeric')
source=(http://downloads.sourceforge.net/elderlore/moe_source.1.0b4.zip)
md5sums=('2e91dedfca7438e460f0a84ea85183c7')

build() {
  cd $srcdir/moe.$pkgver
  
  mkdir -p $pkgdir/usr/bin
  mkdir -p $pkgdir/usr/share/mines-of-elderlore    
  mkdir -p $pkgdir/usr/share/mines-of-elderlore/morgue  
  mkdir -p $pkgdir/usr/share/mines-of-elderlore/movies
  mkdir -p $pkgdir/usr/share/applications
  mkdir -p $pkgdir/usr/share/pixmaps
  
  rm -fr $srcdir/moe.$pkgver/data/music/*
  
  chgrp games $pkgdir/usr/share/mines-of-elderlore/morgue  
  chgrp games $pkgdir/usr/share/mines-of-elderlore/movies

  chmod 770 $pkgdir/usr/share/mines-of-elderlore/morgue  
  chmod 770 $pkgdir/usr/share/mines-of-elderlore/movies
    
  chgrp games $pkgdir/usr/share/mines-of-elderlore/
  chmod 770 $pkgdir/usr/share/mines-of-elderlore/
  
  cp -fr $srcdir/moe.$pkgver/* $pkgdir/usr/share/mines-of-elderlore
  
  echo "cd /usr/share/mines-of-elderlore/
python2 moe-pygame.py" > $pkgdir/usr/bin/mines-of-elderlore
  echo "python /usr/share/mines-of-elderlore/moe-curses.py" > $pkgdir/usr/bin/mines-of-elderlore-term
  
  chmod +x $pkgdir/usr/bin/mines-of-elderlore
  chmod +x $pkgdir/usr/bin/mines-of-elderlore-term
  
  
  
  cp $srcdir/../mines-of-elderlore.png $pkgdir/usr/share/pixmaps/    
  install -D -m644 $srcdir/../mines-of-elderlore.desktop $pkgdir/usr/share/applications
  
 
  
}
