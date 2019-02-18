.. title: fades8.1_released
.. slug: fades81_released
.. date: 2019-02-18 10:49:10 UTC-03:00
.. tags: fades,python,virtualenvs
.. category: 
.. link: 
.. description: 
.. type: text

We're glad to announce the release of fades 8.1.

fades is a system that automatically handles the virtualenvs in the
cases normally found when writing scripts and simple programs, and
even helps to administer big projects.

It will automagically create a new virtualenv (or reuse a previous
created one), installing the necessary dependencies, and execute
your script inside that virtualenv.

You only need to execute the script with fades (instead of Python) and
also mark the required dependencies. More details here:

    http://fades.rtfd.org/


What's new in this release?

- Automatically execute scripts from the web, supporting most common pastebins

- Multiple (and missing) requirement.txt file support, which can now be nested

- Avoid checking package availability if no PyPI dependencies indicated

- Add an option to show the virtualenv path in the system

- Better error/help on missing indicated script or executable from dependency

- Improved logs, PyPI urls, documentation, multiplatform support, and several other small fixes/enhancements


We want to say a big thank you to the following collaborators
that helped to improve and enhance fades in different ways for this
version (in alphabetical order):

    - Andrés Delfino - https://github.com/andresdelfino
    - Iñaki Malerba - https://github.com/inakimalerba
    - Martin Alderete - https://github.com/malderete


To install and enjoy fades...

- If you are in Ubuntu or Debian, you can easily install like this (but probably won't get *latest* fades::

    sudo apt-get install fades

- For not latest debian/ubuntu you have a .deb here (with its Debian source file)::

    http://ftp.debian.org/debian/pool/main/f/fades/fades_8.1-1_all.deb
    http://ftp.debian.org/debian/pool/main/f/fades/fades_8.1-1.dsc

- Install it in Arch is very simple::

    yaourt -S fades

- In any Linux if you have the Snap system::

    snap install fades

- Using pip if you want::

    pip3 install fades

- You can always get the multiplatform tarball and install it in the old fashion way::

    wget http://ftp.debian.org/debian/pool/main/f/fades/fades_8.1.orig.tar.gz
    tar -xf fades_*.tar.gz
    cd fades-*
    sudo ./setup.py install


Help / questions:

- You can ask any question or send any recommendation or request
  in the Telegram group:

    https://t.me/fadesmagic

  ...or to the mailing list...

    http://listas.python.org.ar/mailman/listinfo/fades

  ...or in the #fades IRC channel (in Freenode).

- Also, you can open an issue here (please do if you find any problem!).

    https://github.com/PyAr/fades/issues/new

- The project itself is in

    https://github.com/PyAr/fades

  It's very easy to run latest development version:

    git clone https://github.com/PyAr/fades.git
    cd fades
    bin/fades


Thanks in advance for your time!

