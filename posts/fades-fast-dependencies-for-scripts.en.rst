.. title: fades: FAst DEpendencies for Scripts
.. slug: fades-fast-dependencies-for-scripts
.. date: 2015-02-22 17:14:05 UTC-03:00
.. tags: python, PyAr, proyectos, virtualenv
.. category: 
.. link: 
.. description: 
.. type: text

I traveled on Facu Batista's car to PyConAr 2014. We chatted a lot on this 
Buenos Aires-Rafaela trip and we had the idea of building a tool named 
**fades** to automate virtualenv dependencies.

Last week we released the 1.0 version! Here the press release.


Hello all,


We're glad to announce the release of fades 1.0.
fades, a FAst DEpendencies for Scripts, is a system that automatically
handles the virtualenvs in the simple cases normally found when
writing scripts or simple programs.


It will automagically create a new virtualenv (or reuse a previous
created one for your script), installing or updating the necessary
dependencies, and execute your script inside that virtualenv.


You only need to execute the script with fades (instead of Python) and
also mark the required dependencies. More details here:

https://github.com/PyAr/fades/

To get it:
~~~~~~~~~~

.. TEASER_END

- For debian/ubuntu you have a .deb here:

    http://taniquetil.com.ar/fades/fades-1.0.deb

- Install it in Arch is very simple:

::

    yaourt -S fades

- Using pip if you want:

::

    pip3 install fades

- You can always get the multiplatform tarball and install it in the old fashion way:

::

    wget http://taniquetil.com.ar/fades/fades-1.0.tar.gz
    tar -xf fades-1.0.tar.gz
    cd fades-1.0
    sudo ./setup.py install

Help / questions:
~~~~~~~~~~~~~~~~~

- You can ask any question or send any recommendation or request to the mailing list.

    http://listas.python.org.ar/mailman/listinfo/fades

- Also, you can open an issue here (please do if you find any problem!).

    https://github.com/PyAr/fades/issues/new


Thanks in advance for your time!

