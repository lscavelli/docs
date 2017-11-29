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

Altre portlet sono in fase di realizzazione.

.. _webcontent:

Webcontent portlet
==================

La portlet webcontent consente la visualizzazione di un singolo contenuto informativo nella posizione in cui è posizionata la portlet stessa. L'aspetto del contenuto dipenderà dalla sua struttura dati e dal modello (vista) scelto per la sua visualizzazione.
Lo stesso contenuto informativo, attraverso l'uso di più portlet webcontent, può essere presente in più pagine del sito o più volte nella stessa pagina (in modalità multi istanza), assumendo, in base ai modelli scelti, differenti aspetti.

La scelta del modello può essere effettuata sia nell'editor del contenuto, sia nella finestra di configurazione della portlet.

I modelli possono essere di due tipi: di tipo "lista", quelli utilizzabili nella portlet "contentList" eslusivamente per le righe di una lista; di tipo "base", applicabili al singolo contenuto informativo ed utilizzabili nella portlet "webContent.
I modelli che verranno mostrati nella finestra di configurazione della portlet dipenderanno dalla struttura dati del contenuto selezionato.

Poiché possono essere impostati, per lo stesso contenuto, più modelli, la portlet in fase di visualizzazione del contenuto informativo utilizzerà il seguente ordine di priorità:

1. Modello impostato nella portlet;
2. Modello impostato nell'editor del contenuto;
3. In assenza dei primi due, il primo modello appartenente alla struttura dati del contenuto.

Se il modello non è trovato o non esistono modelli per la struttura del contenuto selezionato, il sistema mostrerà un messaggio di errore.

Selezione manuale del contenuto
-------------------------------
Il contenuto informativo che la portle visualizzerà, viene selezionato, nella modalità manuale, nel pannello di configurazione della portlet. Dopo aver scelto una struttura dati, la finestra mostrerà i contenuti informativi basati sulla struttura selezionata. Cliccare su aggiungi, per selezionate il contenuto.

Selezione dinamica del contenuto
--------------------------------
Se la comunicazione della portlet è attiva (impostabile dalla finestra di configurazione) e nell'URL è presente lo slug di un contenuto informativo valido, questo sarà ricercato e visualizzato nella portlet, indipendentemente dalla presenza di un contenuto impostato manualmente nella portlet. Con tale configurazione una portlet webContent potrebbe visualizzare di default un contenuto informativo e dinamicamente un altro. 
Nella modalità dinamica lo stesso contenuto informativo verrà visualizzato in tutte le portlet webcontent, che avranno la comunicazione impostata su "attiva".

Uno slug di un contenuto informativo può essere presente nell'url nei seguenti modi:

* http://<domain-name>/<page>/<slug-web-content>
* http://<domain-name>?content=<slug-web-content>
* http://<domain-name>/<slug-web-content>

Quest'ultima ipotesi sarà attuabile solo e soltanto se risulterà direttamente assegnata al contenuto informativo una pagina di visualizzazione con la presenza di una portlet webcontent che avrà il parametro "predefinita per questa pagina" impostato su "On".

Condivisione del contentuto
---------------------------
Dal pannello di configurazione è possibile abilitare la condivisione del contenuto informativo sui principali social media. Se la condivisione risulta abilitata, compariranno, a fine testo, sulla destra, le icone dei social attualmente disponibili. Cliccando su queste si aprirà un popup che consentirà lo sharing del content sul rispettivi social. Se al contenuto informativo è associata un'immagine, questa sarà visualizzata nella finestra. Il format dipenderà dalla dimensione dell'immagine.

Abilitazione commenti
---------------------
La portlet webcontent consente l'attivazione del modulo per l'invio e la visualizzazione dei commenti alla fine del contenuto informativo. I commenti, in base alla configurazione che si è scelta, possono essere moderati o immediatamente visibili. All'atto della registrazione di un nuovo commento, una notifica di tipo email parte all'autore del contenuto. I commenti possono essere gestiti nella sezione dei contenuti dal menu posto a destra in corrispondenza del contenuto interessato.

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

