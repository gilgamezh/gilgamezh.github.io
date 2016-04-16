.. title: fades: FAst DEpendencies for Scripts
.. slug: fades-fast-dependencies-for-scripts
.. date: 2015-02-22 17:14:05 UTC-03:00
.. tags: python, PyAr, proyectos, virtualenv
.. category: 
.. link: 
.. description: 
.. type: text

En el viaje a PyConAr 2014 fui y volví en auto con Facu Batista. En esas horas
charlamos sin para un minuto, y entre cosa y cosa se nos ocurrió un proyectito
muy divertido que dimos a llamar **fades**.
Hace unas semanas hicimos el release 1.0. así que acá la gacetilla :)


Hola a todas y todos,

Estamos contentos de anunciar la liberación de fades 1.0.
fades (en inglés: FAst DEpendencies for Scripts) es un sistema que
maneja automáticamente los virtualenvs en los casos simples que
uno normalmente encuentra al escribir scripts o programas pequeños.

Crea automáticamente un nuevo virtualenv (o reusa uno creado previamente
para ese script), instalando o actualizando las dependencias necesarias,
y ejecutando el script dentro de ese virtualenv.

Todo lo que necesitás hacer es ejecutar el script con fades (en lugar de
Python) y también marcar las dependencias necesarias. Más detalles acá:

https://github.com/PyAr/fades/

Para obtenerlo:
~~~~~~~~~~~~~~~

.. TEASER_END

- Para debian/ubuntu hay un .deb acá:

    http://taniquetil.com.ar/fades/fades-1.0.deb

- Instalarlo en Arch es muy simple:

::

    yaourt -S fades

- Podés usar pip si querés:

::
    
    pip3 install fades


- Siempre podés usar el tarball multiplataforma e instalarlo de la manera clásica:

::

    wget http://taniquetil.com.ar/fades/fades-1.0.tar.gz
    tar -xf fades-1.0.tar.gz
    cd fades-1.0
    sudo ./setup.py install


Ayuda / preguntas:
~~~~~~~~~~~~~~~~~~

- Podés hacer cualquier pregunta o mandar una recomendación o pedido en la lista de correo:

    http://listas.python.org.ar/mailman/listinfo/fades

- También podés abrir un issue acá (por favor hacelo si encontrás algún problema!):

    https://github.com/PyAr/fades/issues/new

Desde ya, muchas gracias por tu tiempo!
