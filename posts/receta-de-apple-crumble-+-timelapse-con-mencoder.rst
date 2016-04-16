.. title: Receta de Apple Crumble + Timelapse con Mencoder
.. slug: receta-de-apple-crumble-+-timelapse-con-mencoder
.. date: 2013-06-16 21:35:01 UTC-03:00
.. tags: personal, old_blog, comida, food, mencoder
.. category: 
.. link: http://recetasamericanas.com/2012/01/19/crujiente-de-manzana-apple-crisp
.. description: Receta para hacer un Apple Crumble :)
.. type: text

Copiada de acá pero es tal cual lo hace mi flia.

http://recetasamericanas.com/2012/01/19/crujiente-de-manzana-apple-crisp

Ingredientes:
-------------

    * 6 manzanas grandes
    * 200 g (1 taza) de azúcar
    * 90 g (3/4 taza) de harina
    * 180 g (1/3 taza) manteca (a temperatura de ambiente)
    * 60 ml (1/4 taza) de agua
    * 5 ml (1 cucharita) de canela
    * 2,5 ml (1/2 cucharita) de sal


.. TEASER_END


Receta:
-------

Precalienta el horno a 180°C (350°F) Pela las manzanas y córtalas en trozos medianos. Unos 10 trozos por manzana es lo normal. (Si son trozos demasiado pequeños pierden textura y se convierte en puré… y son demasiado grandes quedan duros y secos.) Coloca los trozos en una bandeja del horno (20×20). Verte la agua encima de una manera uniforme, seguida por la canela y la sal. En un bol pequeño mezcla la harina y azúcar. Añade la mantequilla y  machaca con un tenedor hasta que quedé más o menos hecho una pasta pero con muchas migas también. Distribuye la mezcla por encima de las manzanas. Hornea por unos 40 minutos, hasta que las manzanas se estén caramelizando y esté totalmente dorada encima.

De paso saque fotos mientras lo hice y después arme un timelapse con Mencoder.
------------------------------------------------------------------------------

Pasos: 

* enviar a un archivo los nombres de todas las imágenes::
    
    ls -1tr > files.txt

* Encodear con Mencoder::

    mencoder -nosound -ovc lavc -lavcopts vcodec=mpeg4 -o test_4fps.avi \
    -mf type=jpeg:fps=4 mf://@files.txt

(use 4FPS para 50 imágenes, esto lo hice a ojo)


.. media:: https://www.flickr.com/photos/bolche/9063385970/

