.. title: Fades 2.0
.. slug: fades-20
.. date: 2015-02-28 12:25:16 UTC-03:00
.. tags: fades, PyAr, proyectos, python, virtualenv
.. category: 
.. link: 
.. description: 
.. type: text

Fueron (creo) unas 2 semanas desde que salió el release 1.0 de Fades las que 
demoramos en sacar el 2.0 :). El ritmo estuvo muy bueno y sobre todo largas
charlas de qué camino tomar.
Cuándo salió la 1.0 Robert Collins `nos hizo algunos comentarios sobre xattr <https://twitter.com/gilgamezh/status/571377065053851648>`_ 
, y después de una `linda charla via IRC <https://github.com/PyAr/fades/issues/29>`_ 
fades empezó a hacer honor a la primer palabra de su sigla para mutar a una 
caché de virtualenvs en lugar de tener uno por cada script.
De paso se arreglaron varios errores y se mejoraron muchas cosas.

¿Qué hay de nuevo en esta release?

- Tiene un cache para virtualenvs creados en el sistema; mejora
  la reutilización y velocidad.

- Como resultado del feature anterior, ya no guarda metadata por
  script (*en* el script).

- Permite indicar el nombre del projecto si es diferente al del
  módulo (ej: "import bs4 # fades.pypi beautifulsoup4 == 3.5")

- Soporta requerimientos complejos de versión: (ej: "<2.6,>1.3,!=1.9")

- Maneja paquetes a los que pip les cambia el nombre

- Otros cambios y correcciones menores.


Mas info: https://github.com/PyAr/fades/releases/tag/2.0
