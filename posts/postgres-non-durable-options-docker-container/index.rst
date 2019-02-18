.. title: Postgres non-durable options Docker container.
.. slug: postgres-non-durable-options-docker-container
.. date: 2017-04-09 15:55:48 UTC-03:00
.. tags: docker, postgres, how-to
.. category: 
.. link: 
.. description: How to configure postgres Docker container with non-durable options.
.. type: text

Some weeks ago I was at `Pycamp <http://www.python.org.ar/wiki/PyCamp/2017/>`_ whit LeCoVi 
working on the Pyar website (check the link PyCamp is the best event ever!) and 
I showed him my configuration to speed-up django tests. 
Some days ago he asked me for the config. I think that it'is better to share it 
in my blog, so here I'm.

When you work with a framework like Django, to develop it with the same database 
that you run in production is a really good idea. 
It's really easy using `docker-compose`. And to speed up your tests you can 
configure postgres with its `non-durable options <https://www.postgresql.org/docs/current/static/non-durability.html>`_.

Here my recipe to do it. 

I'm using the `oficial Postgres Docker image <https://hub.docker.com/_/postgres/>`_ 
adding only some scripts::

    FROM postgres:9.4.4
    MAINTAINER gilgamezh <spam@gilgamezh.me>

    COPY docker-entrypoint_db.sh /
    COPY non_durable.sh /
    ENTRYPOINT ["/docker-entrypoint_db.sh"]


Here the content of docker-entrypoint_db.sh. I'm using an environment variable
to enable or disable the non_durable settings:: 
    
    #!/bin/bash

    if [ -v POSTGRES_NON_DURABLE_SETTINGS ]; then 
        cp /non_durable.sh /docker-entrypoint-initdb.d/
    fi 

    # run the default img entrypoint
    /bin/sh /docker-entrypoint.sh postgres

And here the script to change the Postgres configuration::

    #!/bin/bash

    # setting non-durable options 
    # https://www.postgresql.org/docs/current/static/non-durability.html
    echo "Configuring postgres non-durable options."
    # no need to flush data to disk.
    echo "fsync = off" >> /var/lib/postgresql/data/postgresql.conf
    # no need to force WAL writes to disk on every commit. 
    echo "synchronous_commit = off" >> /var/lib/postgresql/data/postgresql.conf 
    # no need to guard against partial page writes. 
    echo "full_page_writes = off" >> /var/lib/postgresql/data/postgresql.conf 

Then in my docker-compose.yml file I'm setting the `POSTGRES_NON_DURABLE_SETTINGS` 
variable:: 

      environment:
        - POSTGRES_PASSWORD=xxxx
        - POSTGRES_NON_DURABLE_SETTINGS=1


With these changes my tests are running a lot faster. 🚀🚀🚀
