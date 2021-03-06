==========
Quickstart
==========

Questa pagina fornisce una rapida introduzione alle principali caratteristiche di Newportal.
Se non hai ancora installato **Newportal** vai alla pagina :ref:`installation`.

.. _widget:

Front end with widgets
=======================

Un **widget** è un componente modulare che aggrega contenuti informativi su una pagina web.
Una sorta di plug-in che consente la pubblicazione di informazioni in porzioni di pagina.
Tramite i widgets lo stesso contenuto è utilizzabile in più pagine o più volte nella
stessa pagina (Multi istanza).
I widgets possono essere trascinate in aree specifiche della pagina in base al
modello di layout adottato. Durante il trascinamento si attiva un indicatore di colore
blue in corrispondenza delle aree di rilascio. All'interno della stessa area sarà
possibile disporre più widgets e ordinarle diversamente. Grazie al supporto
al Drag-and-Drop, le pagine del portale potranno essere riorganizzate rapidamente.

Web Content
===========

I contenuti web sono contenuti strutturati che compongono le pagine del portale.
Si basano essenzialmente sulle Strutture (form per l'acquisizione dei dati informativi)
e sui Modelli (Viste di presentazione dei dati).
Un tool visuale, basato su `Formeo <https://github.com/Draggable/formeo>`_,
consente agevolmente di costruire, in base alle proprie esigenze, strutture semplici
e complesse alle quali sarà possibile associare uno o più modelli (dynamic template).
Lato front-end i widgets possono estrarre Web Content che rispondano a determinate
strutture (ex. news / eventi) ed assumere differenti aspetti in base al modello scelto
per la visualizzazione.

Per ogni struttura ``/admin/structure`` è possibile creare più modelli. Di seguito si
riportano alcuni esempi di viste dinamiche associate alle strutture formeo.

Esempio di modello di tipo lista associato ad una struttura contenente un solo campo
variabile: es. $np714bc8ec8c2a4929bee9319dd31a1207

.. code-block:: html
   :linenos:

    <li class="articles clearfix content_divisor">
        <a href="{!! $np_href !!}" class="content_title">{!! $np_title !!}</a><br />
        <span class="image left"><img src="{!! $np_image !!}" alt="{!! $np_title !!}" class="img-responsive"></span>
        <p>{!! \App\Libraries\sl_text::sommario(strip_tags($np714bc8ec8c2a4929bee9319dd31a1207)) !!}
            @if(strlen(strip_tags($np714bc8ec8c2a4929bee9319dd31a1207))>255)
                <a href="{!! $np_href !!}">Leggi ancora</a>
            @endif
        </p>
        <p class="articles_meta">
            @if(count($np_categories)>0)
                @foreach($np_categories as $category)
                    <a class="articles_category" href="/{!! $np_page !!}?category={!! $category->id !!}">#{!! $category->name !!}</a>,
                @endforeach
            @endif
            Posted by <a href="/{!! $np_page !!}?author={!! $np_author_id !!}" class="articles_author">{!! $np_author_name !!}</a>
            on <time datetime="{!! $np_data_creazione !!}">{!! $np_data_creazione !!}</time>
        </p><br />
    </li>

Oltre all'autore, all'immagine e al titolo, la precedente vista visualizza anche le
categorie associate ai singoli contenuti web. Allo stesso modo potrebbe visualizzare i Tag.

Il successivo esempio riporta una lista semplificata contenente solo titolo e data di creazione.

.. code-block:: html
   :linenos:

    <li class="block-hover">
        <a href="{{ $np_href }}" class="content_title">{!! $np_title !!}</a>
        <div style="font-size:9px">({!! $np_data_creazione !!})</div>
    </li>

Nel successivo esempio, invece, si fa riferimento ad una vista relativa ad un singolo contenuto web.

.. code-block:: html
   :linenos:

    <h3>{!! $np_title !!}</h3>
    by <a href="/video?author={!! $np_author_id !!}" class="articles_author">{!! $np_author_name !!}</a>
    on {!! $np_data_creazione !!}
    <br /><br />
    {!! $np714bc8ec8c2a4929bee9319dd31a1207 !!}

Dynamic Data List
=================
Attraverso i Dynamic Data List è possibile definire un elenco dati dinamico, ovvero
un elenco di contenuti web basato sulla medesima struttura, esportabile nei diversi
formati (excel, csv, xml, txt, etc...). Così come avviene per i Contenuti web, la
creazione dei "Dynamic Data List" richiede l'impostazione di una struttura dati.

Categorization
==============

Newportal consente la creazione di più vocabolari per aggregare un numero quasi infinito
di categorie omogenee.  I vocabolari possono essere associati a più servizi del
portale e resi accessibili separatamente attraverso la sezione "Categorizzazione". 
Contestualmente alle categorie è possibile definire e associare i tag, in modo da
rendere i contenuti facilmente ritrovabili e filtrabili anche lato front-end.

Frontend side
-------------

Con l'uso di appositi widgets sarà possibile creare pagine web complete di menu
di navigazione basati su vocabolari di categorie e tags. Gli elementi che aggregano
i contenuti presenti nella pagina consentiranno di filtrare i dati in base ai
valori dei vocabolari definiti in configurazione o in base alla categoria passata
nell'url, se la comunicazione tra widgets è stata abilitata.

Pages, themes and layouts
=========================

Newportal gestisce sia pagine pubbliche (accessibili a chiunque) che private. 
Le pagine private sono accessibili solo agli utenti membri del sito che possiede
le pagine. Per impostazione predefinita tutte le pagine vengono automaticamente
mostrate nei menu di navigazione. Se si vuole omettere tale visualizzazione, la
pagina dovrà essere creata come nascosta. Le pagine possono essere: - nidificate
ovvero create come sotto-pagine di altre pagine esistenti; - vuote o precompilate,
partendo da dei modelli di pagina predefiniti; - di tipo Widget, URL o Link interno.
In base al tema e al layout scelto, le pagine possono assumere aspetti differenti.
i layout consentono di specificare come i widgets saranno disposte nelle pagine.
Possono essere creati e resi disponibili per lo stesso sito diversi layout. 
Con alcune piccole modifiche sarà possibile utilizzare themes e templates
fully responsive facilmente reperibili su web

User management
===============

Dal pannello di controllo un amministratore può: gestire gli utenti del portale,
raggruppandoli in team di lavoro o inserendoli in organizzazioni gerarchiche; 
assegnare ad utenti e gruppi di utenti i permessi (privilegi di accesso alle
risorse del sistema) o i ruoli (insieme di permessi); accedere a tutti i profili
definiti dal sistema (utente, gruppo, permesso, ruolo, organizzazione).
Se abilitato, il modulo di registrazione per creare i nuovi utenti può essere
liberamente accessibile.
Attraverso la pagina di login gli utenti potranno autenticarsi al portale,
digitando il proprio nome utente (o email) e password, oppure utilizzando alcune
delle opzioni sociali di autenticazione.
Qualsiasi accesso alle risorse protette del sistema effettuato da un utente non
registrato sarà rediretto alla pagina di login.
L'attività degli utenti è registrata. Un utente non amministratore avrà accesso
solo al registro della propria attività. Il sistema consente anche la visualizzazione
delle sessioni attive con possibilità per l'utente amministratore di cancellarle.
