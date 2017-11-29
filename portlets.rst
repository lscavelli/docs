===================
Portlets principali
===================

Nella pagina Quikstart si è fatto cenno alle :ref:`Portlets <portlet>` come elementi aggregatori di contenuti informativi su una pagina web Newportal.
Le portlet attualmente disponibili sono:

* :ref:`webcontent <webcontent>`;
* :ref:`contentlist <contentlist>`;
* navigationpages;
* navigationcat;
* navigationtag;
* organizations.

.. _webcontent:

Webcontent portlet
==================

La portlet webcontent consente la visualizzazione di un singolo contenuto web nella posizione in cui è posizionata la portlet. L'aspetto del contenuto dipenderà dalla sua struttura dati e dal modello (vista) scelto per la visualizzazione.
La scelta del modello può essere effettuata sia nell'editor del contenuto, sia nella finestra di configurazione della portlet.
I modelli possono essere di due tipi: di tipo "lista", quelli utilizzabili nella portlet "contentList" eslusivamente per le righe di una lista; di tipo "base", applicabili al singolo contenuto ed utilizzabili nella portlet "webContent.
I modelli selezionabili nella finestra di configurazione della portlet dipenderanno dalla struttura dati del contenuto selezionato.

Poiché per lo stesso contenuto potrebbero essere impostati più modelli, la portlet in fase di visualizzazione del contenuto utilizzerà, nella scelta del modello, il seguente ordine di priorità:

1. Modello impostato nella portlet;
2. Modello impostato nell'editor del contenuto;
3. In assenza dei primi due, il primo modello appartenente alla struttura dati del contenuto.

Se il modello non è trovato o non esistono modelli per la struttura del contenuto selezionato, il sistema mostrerà un messaggio di errore.

Lo stesso contenuto informativo, attraverso l'utilizzo di più portlet webcontent, può essere presente in più pagine del sito o più volte nella stessa pagina (in modalità multi istanza), assumendo, in base ai modelli scelti, differenti aspetti.

Il contenuto da mostrare viene solitamente impostato nella finestra di configurazione della portlet. In tal caso sarà fisso.

Se la comunicazione della portlet è attiva (impostabile dalla finestra di configurazione) e nell'URL è presente lo slug di un web content valido, questo sarà ricercato e visualizzato nella portlet, indipendentemente dal contenuto fisso impostato. In tal modo una portlet webContent potrebbe visualizzare di default un testo e dinamicamente un altro, in base allo slug del content passato nell'url. Se più portlet webcontent risultano presenti nella pagina è tutte hanno la comunicazione attiva, lo stesso contenuto informativo sarà mostrato in tutte le portlet.

Il contenuto può essere presente nell'url nei seguenti modi:

* http://<domain-name>/<page>/<slug-web-content>
* http://<domain-name>?content=<slug-web-content>
* http://<domain-name>/<slug-web-content>

Quest'ultima ipotesi sarà attuabile solo e soltanto se risulterà direttamente assegnata al contenuto una pagina di visualizzazione con la presenza di una portlet webcontent impostata come "predefinita per questa pagina".

.. _contentlist:

Contentlist portlet
===================

La portlet contentlist visualizza una lista di contenuti formattati in base al modello, di tipo list, scelto
nel pannello di configurazione. Lo stile del contenitore (involucro della lista) è predefinito, ma è possibile
modificarlo, selezionandolo dai template disponibili nella scheda "Altre impostazioni" del pannello di configurazione.
Questi template sono inseriti nella cartella partials del tema scelto.

In questo modo la stessa lista può essere utilizzata in più pagine o più volte nella stessa pagina (Multi istanza),
assumendo, in base ai modelli scelti, aspetti differenti.

Filtraggio in base ai Tags e Categorie
--------------------------------------
I contenuti della lista possono essere filtrati in base ai tags e categorie definite nel sito.
La portlet contentlist in fase di visualizzazione imposterà i filtri in base al seguente ordine di priorità:

1. Parametri ``tag`` e ``category`` impostati nell'url (Se la comunicazione è attiva);
2. Tags e categories del web content passato nella URL (Se la comunicazione è attiva);
3. Tags e categories impostati dal pannello di configurazione della portlet (Se la comunicazione è disattiva o i punti precedenti non producono un risultato).

Filtraggio in base alle strutture dati
--------------------------------------

Filtraggio in base all'autore del contenuto
-------------------------------------------

Visualizzazione dei content più popolari
----------------------------------------

Ordinamento delle voci
----------------------

