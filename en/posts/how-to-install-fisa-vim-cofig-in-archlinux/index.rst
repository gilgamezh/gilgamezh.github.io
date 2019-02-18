.. title: How to install Fisa-vim-cofig in Archlinux
.. slug: how-to-install-fisa-vim-cofig-in-archlinux
.. date: 2014-03-15 15:22:44 UTC-03:00
.. tags: python, vim, how-to
.. category: 
.. link: 
.. description: 
.. type: text

.. image:: /images/fisa-dev-config.png 

`Fisa-vim-config <https://github.com/fisadev/fisa-vim-config/>`_ 
es una excelente configuración para Vim que recopila muchos 
plugins y los pone a funcionar de una manera muy simple. 
Esta desarrollada por @fisadev. Agradecimientos para él por permitir 
tener un vim con esteroides muy útil para developers n00bs como yo :).

.. TEASER_END

No pude hacerlo funcionar en  mi Archlinux de una sola vez. Primero que 
nada encontre que Vim en arch no está compilado con Python, por lo que hay 
que instalar gVim (que reemplaza el vim por default por uno compilado con python.

Luego de instalar gVim seguía sin funcionar, lo abandone hasta que ayer 
leí una mail en la lista de pyar con un problema similar al mio y la solución 
era tan simple!! Resulta que gVim está compilado con python-2.7 y en Arch 
python3 es el default. Por lo tanto hay que utilizar pip2 para instalar 
todas las dependencias!! 
(acá el hilo con la consulta de Matuvarela http://listas.python.org.ar/pipermail/pyar/2014-March/028366.html )

En resumen, si querés tener fisa-vim-dev funcionando en Arch tenes que usar 
gvim en lugar de vim, pip2 en lugar de pip y tener en cuenta que el paquete 
exuberant-ctags es extra/xtags.
Lo único que cambia es este punto de la guia de instalación en el repo oficial. 

Dependencies::

    sudo pacman -Sy gvim ctags git python2-pip
    sudo pip2 install dbgp vim-debug pep8 flake8 pyflakes isort


