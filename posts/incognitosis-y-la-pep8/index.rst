.. title: Incognitosis y la PEP8
.. slug: incognitosis-y-la-pep8
.. date: 2015-03-14 10:22:44 UTC-03:00
.. tags: PEP8, python, incognitosis
.. category: 
.. link: 
.. description: 
.. type: text

Hace un tiempo trabajando con `fades <https://github.com/PyAr/fades>`_ Facu me propuso
"estirar" el "Maximum Line Length" para probar si resultaba un poco más cómodo.
A mi me pareció perfecto ya que entiendo que deben quedar muy pocas terminales de 80 
columnas.
Eso sí antes de dar un paso adelante confirmamos con la `PEP8 <https://www.python.org/dev/peps/pep-0008/#maximum-line-length>`_ 
que se puede llevar hasta 100 caracteres, sin romper esta santa ¿ley?.

    Some teams strongly prefer a longer line length. For code maintained 
    exclusively or primarily by a team that can reach agreement on this issue, 
    it is okay to increase the nominal line length from 80 to 100 characters 
    (effectively increasing the maximum length to 99 characters), provided 
    that comments and docstrings are still wrapped at 72 characters. 

Así que ahí fuimos. Como yo tengo una linea que me marca ese límite esto fue lo 
que cambié en mi .vimrc

:: 

    function! ConditionalLoad()
    highlight ColorColumn guibg=PaleTurquoise1
    if getcwd() =~ $HOME . "/code/fades/*"
        set colorcolumn=99
    else
        set colorcolumn=80
    endif
    endfunction
    autocmd BufRead *.py call ConditionalLoad()
    autocmd BufRead *.rst call ConditionalLoad()

El código de esa función es de Facundo.

El punto del cual tomé especial nota es que para los comentarios y docstrings 
la PEP8 recomienda mantenerse dentro de los 72 caracteres

    that comments and docstrings are still wrapped at 72 characters.

Hoy hice click en mi RSS sobre una nota de Incognitosis (a quién normalmente 
leo por RSS) y me llamó la atención el hermoso diseño del blog.
Así que dejé `un comentario <http://www.javipas.com/2015/03/13/usb-c-futuro-estandar/comment-page-1/#comment-87318>`_. 
Apenas termine de escribir el comentario me acordé de los 72 chars y fui a comprobarlo

.. image:: /images/javipass_pep8.png 

Efectivamente la causa de que el blog de Javi Pastor sea tan cómodo para la 
lectura es su respeto por la PEP8!! 

Ya que estamos les recomiendo que no dejen de prestarle un ojo a `Incognitosis <http://www.javipas.com>`_,
es una de los pocos blogs que llevo años leyendo.


