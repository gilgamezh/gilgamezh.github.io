.. title: Tmux tip
.. slug: tmux-tip
.. date: 2014-05-24 12:19:26 UTC-03:00
.. tags: tmux, vim, irssi 
.. category: 
.. link: 
.. description: 
.. type: text

Hace poco tiempo que tmux es mi "manejador" (?) de terminales por defecto 
junto con tmuxp. Tmuxp me permite tener templates (un yaml) para diferentes 
proyectos/tareas. ( es muy muy útil cuando ante alguna situación de emergencia 
tenés que levantar ssh contra 10 servidores diferentes).

.. image:: /images/tmux.png

En mi día a día utilizo mucho software que corre en la consola. Los 2 que más 
utilizo son irssi y vim. Hacer funcionar tmux,irssi y vim juntos 
(cada uno con sus plugins) me costó bastante, así que comparto un tip con el 
que resolví algunos problemas entre ellos.

Los problemas que tenía eran los siguientes:

* tmux no funciona con 256 colores con la configuración standard.
* Vim se ve muy feo sin 256 colores.
* Cuando seteaba TERM=xterm-256color irssi dejaba de funcionar bien (no funciona el "auto-scroll" con las lineas nuevas)
* Al conectarme a algún servidor por ssh vi/vim se quejaban de mi variable $TERM. (E558: Terminal entry not found in terminfo 'screen-256color' not known. Available builtin terminals are:.... )

La solución es muy simple, pero creo que vale la pena el tip porque tuve 
que probar varias configuraciones diferentes.

En mi .zshrc (es lo mismo para .bashrc) puse::

    # for tmux colors
    export TERM=screen-256color
    # and it is to avoid remote host problems with $TERM
    alias ssh='TERM=xterm ssh'

En .tmux.conf únicamente esto::

    # set 256 colors
    set -g default-terminal "screen-256color"
    set -g terminal-overrides 'xterm:colors=256'
     
