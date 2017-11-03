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

La portlet webcontent consente di visualizzare a video un singolo contenuto web appartenente ad una qualsiasi struttura di dati.
L'aspetto del contenuto dipenderà dal modello scelto per la sua visualizzazione.
Il modello può essere impostato sia nell'editor del contenuto o direttamente nella finestra di configurazione della portlet.
In base alla struttura del contenuto la finestra di configurazione mostrerà, per la selezione, diverse viste di tipo "base".

La portlet in fase di visualizzazione del contenuto utilizzerà il modello in base alla seguente ordine di priorità:

1. Modello selezionato nella portlet;
2. Modello del contenuto selezionato;
3. Il primo modello della struttura del contenuto.

Se il modello, per il contenuto selezionato, non è trovato, o non è stato impostato, il sistema mostrerà un messaggio di errore.

Il contenuto da mostrare può essere impostato nella finestra di configurazione della portlet. In tal caso sarà fisso.
Lo stesso contenuto informativo, attraverso questo tipo di portlet, può essere utilizzato in più pagine o più volte nella
stessa pagina (Multi istanza), assumendo, in base al modello scelto, anche aspetti differenti.

Se la comunicazione è attiva (impostabile dalla finestra di configurazione) e nell'URL è presente lo slug di un content
web valido, questo sarà ricercato e visualizzato nella portlet, indipendentemente dal contenuto fisso se impostato.

Il contenuto può essere presente nell'url nei seguenti modi:

* http://<domain>/<page>/<slug-web-content>
* http://<domain>?content=<slug-web-content>


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

