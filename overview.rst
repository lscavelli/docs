========
Overview
========

Requirements
============

    E' necessario assicurarsi che il server soddisfi i seguenti requisiti:

    * PHP >= 7.0.0
    * OpenSSL PHP Extension
    * PDO PHP Extension
    * Mbstring PHP Extension
    * Tokenizer PHP Extension
    * XML PHP Extension

.. note::

	NewPortaL si basa su Laravel ver. 5.5, pertanto i requisiti sono quelli richiesti dal framework Laravel

.. _installation:

Installation
============

    Si presume che, sia in locale che su uno spazio hosting Linux con accesso SSH,
    siano installati i pacchetti Node.js - Npm - Bower - PHP - Composer.
    Una valida alternativa sarebbe l'installazione di Homestead in quanto dispone di tutti
    i pacchetti necessari.

Su una macchina di sviluppo
----------------------------

.. code-block:: bash

    # importare il progetto da github repository
    # posizionarsi nella document root ex cd /c/www
    git clone https://github.com/lscavelli/newportal.git newportal

    # installare le dipendenze di Back end
    cd newportal
    composer install

    # copiare il file di environment
    cp .env.example .env

    # generare la chiave del portale
    php artisan key:generate

    # impostare l'accesso al DB all'interno del file .env
    # effettuare la generazione delle tabelle nel DB
    # attendere qualche minuto, le tabelle Cities e Countries contengono molti dati
    php artisan migrate --force --seed

    # rendere scrivibile le seguenti dir
    chmod -R 777 storage
    chmod -R 777 bootstrap/cache
    chmod -R 774 config

    # avviare il server web - http://127.0.0.1:8000
    php artisan serve

    # modificare il file hosts da /etc/hosts (linux)
    # oppure C:\Windows\System32\drivers\etc\hosts (windows), inserendo:
    127.0.0.1 newportal.dev

    # installare le dipendenze di front end
    cd public
    bower install

    # credenziali per login - http://newportal.dev:8000/login
    username: admin@example.com
    password: admin

Su uno spazio hosting Linux con accesso SSH
-------------------------------------------

.. code-block:: bash

    # nomesito.io (Domain name)
    # httpdocs (Document root)

    # verificare che la dir httpdocs sia vuota, dopodiché eliminarla
    rm -rf httpdocs

    # se già esiste la dir newportal rimuoverla con rm -rf newportal
    # importare il progetto laravel fuori dalla document root
    git clone https://github.com/lscavelli/newportal.git newportal

    # creare un link simbolico alla dir public
    # dopo la creazione del link verificare la funzionalità, entrando nella cartella - cd httpdocs
    ln -s newportal/public httpdocs

    # installare le dipendenze di Back end
    cd newportal
    composer install

    # copiare il file di environment
    cp .env.example .env

    # generare la chiave del portale
    php artisan key:generate

    # eliminare la linea APP_ENV dal file .env (questo verrà impostato su production)
    # eliminare la linea APP_DEBUG dal file .env (questo verrà impostato su false)
    # impostare nel file .env la variabile SESSION_DRIVER su database

    composer dump-autoload

    # impostare i dati di accesso al DB nel file .env
    # effettuare la generazione delle tabelle nel DB
    # Attendere qualche minuto. Le tabelle Cities e Countries contengono molti dati
    php artisan migrate --seed

    # abilitare la scrittura per alcune dir
    chmod -R o+w storage
    chmod -R o+w bootstrap/cache

    # ottimizzare l'autoloader e mettere in cache alcuni file
    composer dumpautoload -o # oppure con composer dump-autoload --optimize --no-dev
    php artisan config:cache
    php artisan route:cache
    php artisan optimize --force # deprecato

    # una volta che si esegue il comando config:cache.
    # due nuovi file saranno creati in bootstrap/cache.
    # Questi sono config.php e services.php
    # Rieseguire il comando se si cambiano i percorsi e le configurazioni
    # Con il comando route:cache viene creato nella cache un terzo file, route.php.

    # Installo le dipendenze di front end
    cd httpdocs
    bower install

    # credenziali per login - http://<domain-name>/login
    username: admin@example.com
    password: admin


License
=======

Licensed using the `MIT license <http://opensource.org/licenses/MIT>`_.

    Copyright (c) 2017 LFG Scavelli <https://github.com/lscavelli>

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.


Contributing
============

    Per contribuire al progetto si dovrà installare in locale newportal seguendo
    la :ref:`procedura di installer <installation>` indicata nella presente guida.
    Si dovranno installare anche tutte le dipendenze di backend e frontend, utilizzando
    rispettivamente Composer e bower.
    Al termine dei lavori di integrazione/modifica sarà sufficiente aprire una pull request su GitHub

    Gli errori, ma anche semplici suggerimenti, possono essere segnalati attraverso
    il webform di contatto del sito web o l'email newportalclub@gmail.com.

    Sarebbe auspicabile che le vulnerabilità di protezione venissero segnalate con urgenza
    esclusivamente all'indirizzo di posta elettronica newportalclub@gmail.com

    E' possibile contribuire al progetto anche in ambiti diversi dallo sviluppo software,
    ovvero nella traduzione dei testi, nell'analisi, nell'eseguire test di unità, nel design etc...

    Ogni contributo risulterà sempre prezioso e utile al miglioramento del progetto.
