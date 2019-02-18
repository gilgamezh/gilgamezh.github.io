.. title: fades8.1_released
.. slug: fades81_released
.. date: 2019-02-18 10:49:10 UTC-03:00
.. tags: fades,python,virtualenvs
.. category: 
.. link: 
.. description: 
.. type: text

Hola a todas y todos,

Estamos encantados de anunciar la liberación de fades 8.1.

fades es un sistema que maneja automáticamente los virtualenvs en los
casos que uno normalmente encuentra al escribir scripts y programas
pequeños, e incluso ayuda a administrar proyectos grandes.

Crea automáticamente un nuevo virtualenv (o reusa uno creado previamente)
instalando las dependencias necesarias, y ejecutando el script
dentro de ese virtualenv.

Todo lo que necesitás hacer es ejecutar el script con fades (en lugar de
Python) y también marcar las dependencias necesarias. Más detalles acá:

http://fades.rtfd.org/


¿Qué hay de nuevo en esta release?

- Ejecuta automaticamente scripts desde la web, soportando los pastebines más comunes

- Soporta múltiples (o inexistentes) archivos requirement.txt, los cuales también pueden estar anidados

- Evita revisar la disponibilidad en PyPI si no se indicaron dependencias

- Ofrece una opción para mostrar el path del virtualenv en el sistema

- Mejor indicación/ayuda cuando no se encuentra el script indicado o el ejecutable de la dependencia

- Trae mejoras en logs, urls de PyPI, documentación, soporte multiplataforma, y varias otras mejoras y correcciones menores


Queremos darles muchas gracias a los siguientes colaboradores que ayudaron a mejorar a fades de distintas maneras para esta versión (en orden alfabético):

- Andrés Delfino - https://github.com/andresdelfino
- Iñaki Malerba - https://github.com/inakimalerba
- Martin Alderete - https://github.com/malderete


Para instalar y disfrutar fades:

- Si estás en Ubuntu o Debian, podés facilmente instalarlo así (aunque probablemente no obtengas la *última* versión::

   sudo apt-get install fades

- Para debian/ubuntu que no sea lo último, acá hay un .deb (con su respectivo archivo fuente Debian)::

   http://ftp.debian.org/debian/pool/main/f/fades/fades_8.1-1_all.deb
   http://ftp.debian.org/debian/pool/main/f/fades/fades_8.1-1.dsc

- Instalarlo en Arch es muy simple::

   yaourt -S fades

- En cualquier Linux si tenés el sistema Snap::

   snap install fades

- Podés usar pip si querés::

   pip3 install fades

- Siempre podés usar el tarball multiplataforma e instalarlo de la manera clásica::

   wget http://ftp.debian.org/debian/pool/main/f/fades/fades_8.1.orig.tar.gz
   tar -xf fades_*.tar.gz
   cd fades-*
   sudo ./setup.py install


Ayuda / preguntas:

- Podés hacer cualquier pregunta o mandar una recomendación o pedido en el grupo de Telegram:

   `https://t.me/fadesmagic`

...o en la lista de correo...

http://listas.python.org.ar/mailman/listinfo/fades

...o en el canal de IRC #fades en Freenode.

- También podés abrir un issue acá (por favor hacelo si encontrás algún problema!):

https://github.com/PyAr/fades/issues/new

- El proyecto en sí está en

https://github.com/PyAr/fades

Es muy fácil ejecutar la última versión de desarrollo:

git clone https://github.com/PyAr/fades.git
cd fades
bin/fades


Desde ya, muchas gracias por tu tiempo!
