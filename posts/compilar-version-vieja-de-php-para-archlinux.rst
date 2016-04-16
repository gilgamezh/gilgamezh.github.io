.. title: Compilar versión vieja de PHP para Archlinux
.. slug: compilar-version-vieja-de-php-para-archlinux
.. date: 2015-02-28 12:17:52 UTC-03:00
.. tags: archlinux, PHP, how-to 
.. category: 
.. link: 
.. description: 
.. type: text

Archlinux siempre tiene la versión más nueva de todo, eso tiene muchas cosas
positivas.
Algo que suele pasar es que tenemos que usar algo que está productivo y que 
tiene una versión *mucho* más vieja que la instalada.
Hace poco tuve que laburar con un Drupal que estaba usando PHP 5.3 y no me 
quedó otra que compilarlo. 
Así que acá dejo los pasos de cómo hacerlo (básicamente la linea del configure).

* Descargar el source en /usr/local/src.

* Hacer un symlink en /usr/include/freetype2/freetype/freetype.h -> ../freetype.h
  (sin esto da un error porque no encuentra freetype.h)

* Ejecutar configure, make y make install::


    ./configure --enable-mbstring --with-mysql --with-mysqli --with-zlib \
    --with-png-dir=/usr --with-jpeg-dir=/usr \ 
    --with-freetype-dir=/usr/include/freetype2/ --with-curl --with-gettext \
    --with-pdo-mysql --with-pdo-sqlite --with-bz2 \
    --prefix=/usr/local/php-5.3.29 --with-libdir=lib64 --with-gd \
    --with-libdir=lib64 --enable-cgi --enable-sockets --with-mcrypt \
    --with-xpm-dir=/usr

    make
    make install

* Hacer un symlink de /usr/local/php-5.3.29 a /usr/local/php

* Copiar el php.ini que tengamos a /usr/local/php/lib

* Si usamos Apache en httpd.conf hay que hacer un *Include* de 
  /etc/httpd/conf/extra/httpd-fastcgid.conf

