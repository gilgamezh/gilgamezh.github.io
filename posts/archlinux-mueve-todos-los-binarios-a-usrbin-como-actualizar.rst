.. title: Archlinux mueve todos los binarios a /usr/bin. Cómo actualizar?
.. slug: archlinux-mueve-todos-los-binarios-a-usrbin-como-actualizar
.. date: 2013-08-24 17:32:23 UTC-03:00
.. tags: tutoriales, archlinux
.. category: 
.. link: 
.. description: 
.. type: text

Hace ya bastantes días que cualquier que intente actualizar su Archlinux se 
va a encontrar con  un error de este tipo::

    error: failed to commit transaction (conflicting files)
    filesystem: /bin exists in filesystem

Si son precavidos y están suscriptos a las listas de correo de Arch se 
enteraron con tiempo, de cualquier manera los pasos a seguir están detallados 
acá :https://www.archlinux.org/news/binaries-move-to-usrbin-requiring-update-intervention/

.. TEASER_END

Aprovecho que hoy tengo un rato para actualizar mi noteb y copio mi 
experiencia por si a alguien le sirve:

    1) Fix any non-official packages with files in /bin, /sbin or /usr/sbin 
    to put those files in /usr/bin. The list of packages that are not in a 
    repo that need to be fixed can be generated using:

    $ pacman -Qqo /bin /sbin /usr/sbin | pacman -Qm -

.. code-block:: bash 

   gilgamezh ~ $ pacman -Qqo /bin /sbin /usr/sbin | pacman -Qm -
   foo2zjs 20121110-1
   grub 0.97-21
   foo2zjs 20121110-1
   grub 0.97-21

Encontre estos 2 paquetes, foo2zjs lo uso para mi impresora 
(hp laserjet 1005p) y bueno grub... tendré que actualizar a Grub2.

Siguiendo los pasos de la wiki de arch:

.. code-block:: bash 

   gilgamezh ~ $ sudo pacman -S grub-bios
   [sudo] password for gilgamezh:
   resolviendo dependencias...
   verificando conflictos...
   :: grub-common y grub están en conflicto. ¿Quitar grub? [s/N] s

   Paquetes (3): grub-0.97-21 [quitando]  grub-common-2.00-2  grub-bios-2.00-2

   Tamaño Total de Descarga:  4,32 MiB
   Tamaño Total Instalado:    15,08 MiB
   Tamaño neto a actualizar:  13,04 MiB

   :: ¿Continuar con la instalación? [S/n] s
   :: Recuperando paquetes ...


   # modprobe dm-mod
   # grub-install --target=i386-pc --recheck --debug --force /dev/sdaX
   # chattr -i /boot/grub/i386-pc/core.img
   # chattr +i /boot/grub/i386-pc/core.img

**OJO: /boot/grub/menu.lst se guarda como .pacnew hay que renombrarlo!**

Después:

.. code-block:: bash

   gilgamezh ~ $ sudo grub-mkconfig -o /boot/grub/grub.cfg
   Generando grub.cfg...
   Encontrada imagen de linux: /boot/vmlinuz-linux
   Encontrada imagen de memoria inicial: /boot/initramfs-linux.img
   hecho

(restart y con suerte todo funca bien)

Siguiendo con la migración a /usr/bin 

    Also check packages installed from non-official repos using:
    $ paclist <repo> | awk ' { print $1 } ' | pacman -Ql - | grep ' /s\?bin/\| /usr/sbin/' ' } '

Yo no uso repositorios "non-official"

    3) If you have files in /bin, /sbin or /usr/sbin that are unowned by any package, you need to move them. Find a list using:

    $ find /bin /sbin /usr/sbin -exec pacman -Qo -- {} + >/dev/null

En mi caso no tuve resultados de este find.
Después ejecute:

.. code-block:: bash 

   # pacman -Syu --ignore filesystem,bash
   # pacman -S bash
   # pacman -Su

Actualizó como 500 megas y todo 10 puntos :)
